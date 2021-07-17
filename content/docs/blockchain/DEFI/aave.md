---
title: AAVE
weight: 2
bookToc: true
---

# AAVE
- Aave is a decentralized non-custodial liquidity market protocol where users can deposit to provide liquidity and earn income and  borrowers are able to borrow, either over collaterized perpetually, or under collaterized through (one-block liquidity (flash loans )).  

- Aave allows you to withdraw your funds from the pool on demand or export tokenized version of your lender (aTokens) which can be treated as a separate asset token.   

- AAVE is governed by the Aave protocol governance, AAVE is used to vote and decide on the outcome of Aave improvement proposals. AAVE can also be staked within the protocol safety module to provide security to depositors. Stakers earn rewards and fees from the protocol.   

- Total supply of AAVE will be 16 million, 13 of these will be redeemed by LEND token holders, and 3M will be allocated to the AAVE reserve. Staking on the safety module will feature plain AAVE alongside AAVE/Eth pair, where the latter will use Balancer to incentivize market liquidity. 

- The community can decide to distribute ecosystem incentives for certain assets or offer rewards for applications built on top of AAVE. 

- Governance is a 5 step process, First community creates an AIP, Secondly the Community evaluates and provides feedback for the AIP, Thirdly there has been a communal shift to proposal and implement said AIP, 4, the genesis team implements the proposal and submits the AIP to be voted on. Lastly, the governance evaluates the implementation and approves or rejects the proposal

- Two types of governance polices, protocol polices and market polices. Protocol polices govern the behavior of AAve including risks, improvement, and incentives, and market policies define the context of each market within the protocol. 
---
# AAVE Lending Pool (L2P)
- Lending Pool is the main contract of the Aave protocol

- L2P is a lending platform aggregator for the aave lending pool to inhibit the use of under collateralize loans for specific protocols and dapps. 

- Two type of providers liquidity provided on over-collartierized lending platforms like Aave, compound , dydx. These agents using these platforms who have unused collateral could delegate these borrowing lines to L2P. 

- Secondly there can be direct agents who provide liquidity to the L2P protocol.

- These agents act as liquidity providers for specific protocols, these protocols then can spread these credit lines over multiple lending platforms including L2P, and Aave. Note a pool here refers directly to the individual protocol in which a lender has delegated credit to, it does refer to a lending platform. Once the loans are spreads across the optimal lending platform the borrower can then collect there money. When the borrower returns to pay there money, they must pay the interest for each lending platform, the interest for each liquidity provider as well as a reserve to L2P which is used in the case of default. In the case of default this reserve is then used to pay these accounts, if the reserve does not cover it fully it is then on the liquidity providers to pay off there loans.

- Note that once loans have been made by liquidity providers for a given pool, it it is possible the individual loans on each lending pool to change, this can be done through the use of flash loans between lending platforms. 

- There has been future talk for L2P to implement credit default swaps allowing liquidity providers to buy these "insurance against default" where another actor would pay off the default in the case of such an event, else-wise the liquidity provider would be paying monthly premium to the CDS agent, through the use of a smart contract. 


# Basic Escrow Contract Solidity Examples
---
- These notes are from [Building Smart Contracts on AAVE](https://www.chainshot.com/learn/aave) and do a fantastic job explains how to work with smart contracts and some DEFI protocols. THe examples below are to help me remember some of the more novel aspects of calling external contracts when working with crypto.  
This is an good example of using payable solidity ^.0.50 +  
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.7.5;

contract Escrow {
    
    address payable public depositor;
    address payable public  beneficiary;
    address payable public arbiter;

    constructor(address payable arbiter_, address payable beneficiary_) payable {
        arbiter = arbiter_;
        depositor = msg.sender;
        beneficiary= beneficiary_;
    }

    function approve() external payable {
        require(msg.sender == arbiter);
         beneficiary.transfer(address(this).balance);
    }
}

```
This example follows use AWETh (aave interest bearing wrapper Ether) to earn interest on money being held in escrow. Doing this we take advantage of a AAVE Weth gateway and send ethereum to it, to be transferred to WETh, this is then transferred to aWETH an interest bearing asset, we can then withdraw the aWeth and get this eventually back to ETH.  The example shows working with external contracts, sending ethereum and converting to tokens.  It is also an example of using the receive function making a contract able to receive funds.  
```
pragma solidity ^0.7.5;

import "./IERC20.sol";
import "./IWETHGateway.sol";

contract Escrow {
    address payable arbiter;
    address payable depositor;
    address payable beneficiary;
    uint256 org_amount;

    IWETHGateway gateway = IWETHGateway(0xDcD33426BA191383f1c9B431A342498fdac73488);
    IERC20 aWETH = IERC20(0x030bA81f1c18d280636F32af80b9AAd02Cf0854e);

    constructor(address payable _arbiter, address payable _beneficiary) payable {
        arbiter = _arbiter;
        beneficiary = _beneficiary;
        depositor = msg.sender;

        gateway.depositETH{value: msg.value}(address(this), 0);
        org_amount = msg.value;
    }

    //Smart contracts can not automatically receive funds must use this to do so. This can only be used once per contract
    receive() external payable {
    }
    function approve() external {
        require(msg.sender == arbiter);
        aWETH.approve(address(gateway), aWETH.balanceOf(address(this)));
        //Withdraw assumes that the gateway has approval
        gateway.withdrawETH(type(uint256).max, address(this));
        beneficiary.transfer(org_amount);
        depositor.transfer(address(this).balance);
    }
}
```
Below is a similar example to the one below but instead of starting with ETH we get the depositor to transfer DAi to the contract in the constructor, we then add this to a lending pool where it is converted to aDai from here this is an interest bearing assets and we can approve for the pool to withdraw it and send it to when we want.  
```
pragma solidity ^0.7.5;

import "./IERC20.sol";
import "./ILendingPool.sol";

contract Escrow {
    address arbiter;
    address depositor;
    address beneficiary;
    uint256 amount;

    // the mainnet AAVE v2 lending pool
    ILendingPool pool = ILendingPool(0x7d2768dE32b0b80b7a3454c06BdAc94A69DDc7A9);
    // aave interest bearing DAI
    IERC20 aDai = IERC20(0x028171bCA77440897B824Ca71D1c56caC55b68A3);
    // the DAI stablecoin 
    IERC20 dai = IERC20(0x6B175474E89094C44Da98b954EedeAC495271d0F);

    constructor(address _arbiter, address _beneficiary, uint _amount) {
        arbiter = _arbiter;
        beneficiary = _beneficiary;
        depositor = msg.sender;
        amount = _amount;
        dai.transferFrom(depositor, address(this), _amount);
        dai.approve(address(pool), _amount);
        pool.deposit(address(dai), _amount, address(this), 0);
    }

    function approve() external {
        require(msg.sender == arbiter);
        aDai.approve(address(pool), aDai.balanceOf(address(this)));
        pool.withdraw(address(dai), amount, beneficiary);
        pool.withdraw(address(dai), aDai.balanceOf(address(this)), depositor);
    }
}

```
Below is a simple example of a no loss lottery system similar to that of Pooltogether. How this works is simple the 'lottery prize' is the communal interest given from investing dai into aDai through AAVE. The communal interest given is randomly distributed to the winner. The rest of the players simply get their initial amount back. 
```
//SPDX-License-Identifier: MIT
pragma solidity ^0.7.5;

import "./IERC20.sol";
import "./ILendingPool.sol";

contract Lottery {
	// the timestamp of the drawing event
	uint public drawing;
	// the price of the ticket in DAI (100 DAI)
	uint ticketPrice = 100e18;
	uint init_;
	mapping(address => bool) ticketBought;
	mapping(uint => address) indexed_tickets;
	uint ticketNum = 0;
	ILendingPool pool = ILendingPool(0x7d2768dE32b0b80b7a3454c06BdAc94A69DDc7A9);
	IERC20 aDai = IERC20(0x028171bCA77440897B824Ca71D1c56caC55b68A3); 
	IERC20 dai = IERC20(0x6B175474E89094C44Da98b954EedeAC495271d0F);


	
	constructor() {
		//Now has been depreceated now use block.timestamp
        drawing = block.timestamp + 1 weeks;
		init_ =  block.timestamp;
	}

	function purchase() external {
		require(ticketBought[msg.sender] == false);
        if(dai.transferFrom(msg.sender, address(this), ticketPrice) == true) {
			ticketBought[msg.sender] == true;
			indexed_tickets[ticketNum] = msg.sender;
			ticketNum +=1;
		}
		dai.approve(address(pool), ticketPrice);
		pool.deposit(address(dai), ticketPrice, address(this), 0);
	}

	event Winner(address);

	function pickWinner() external {
        require(block.timestamp > drawing);
		uint randomval = (block.timestamp + init_) % ticketNum;
		address winner = indexed_tickets[randomval];
		emit Winner(winner);
		aDai.approve(address(pool), type(uint256).max);
		uint totalval = ticketNum * ticketPrice;
		uint interest_acrued = aDai.balanceOf(address(this)) - totalval;
		for(uint i =0; i < ticketNum; ++i) {
			if(indexed_tickets[i] != winner) {
				//pool.withdraw(address(dai), ticketPrice+interest_acrued, indexed_tickets[i]);
				pool.withdraw(address(dai), ticketPrice, indexed_tickets[i] );
			}
		}
		pool.withdraw(address(dai), type(uint256).max , winner );
	}
}
```
Below is an example of a collaterized group using AAVE, the idea here is simple allow users to take advantage of larger collateral when they need to borrow money, this sort of group relies on some trust between members where members must repay the group as a whole. If members want to withdraw then the group profits/assets are divided equally with interested accrued between all.
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.7.5;

import "./IERC20.sol";
import "./ILendingPool.sol";

contract CollateralGroup {
	ILendingPool pool = ILendingPool(0x7d2768dE32b0b80b7a3454c06BdAc94A69DDc7A9);
	IERC20 dai = IERC20(0x6B175474E89094C44Da98b954EedeAC495271d0F);
	IERC20 aDai = IERC20(0x028171bCA77440897B824Ca71D1c56caC55b68A3); 

	uint depositAmount = 10000e18;
	address[] members;
	mapping(address => bool) isMember;

	constructor(address[] memory _members) {
        members = _members;
		for(uint i =0; i < members.length; ++i) {
			dai.transferFrom(members[i], address(this), depositAmount);
			isMember[members[i]] = true;
		}
		dai.approve(address(pool), type(uint256).max);
		pool.deposit(address(dai), dai.balanceOf(address(this)), address(this), 0);
	}

	function withdraw() external {
		require(isMember[msg.sender] == true);
		aDai.approve(address(pool), type(uint256).max);
		pool.withdraw(address(dai), aDai.balanceOf(address(this)), address(this));
		uint portion = dai.balanceOf(address(this)) / members.length;
		for(uint i = 0; i < members.length; ++i) {

			dai.transferFrom(address(this), members[i], portion );
		}
	}

	function borrow(address asset, uint amount) external {
		require(isMember[msg.sender] == true);
		pool.borrow(asset, amount, 1, 0, address(this));
		uint h;
        //Note this function here is how we get the last variable when 6 variables are returned
		(,,,,,h) = pool.getUserAccountData(address(this));
        //Health Factor of Aave borrowing
		require(h > 2e18);
		IERC20 assettmp = IERC20(asset);
		assettmp.transferFrom(address(this), msg.sender, amount);
		
	}

	function repay(address asset, uint amount) external {
		IERC20 assettmp = IERC20(asset);
		assettmp.transferFrom(msg.sender, address(this), amount);
		assettmp.approve(address(pool), amount);
		pool.repay(asset, amount, 1, address(this));
	}
}
### Flash Loans
```
Below is a simple example of a AAVE flash loan where we are loaning 100k dai, selling it to a governance token, voting with such governance token, and then buying all in the same transaction. There are a few components to this mostly the ```flashvote``` and ```executeOperation``` function. Note: all contracts using flash loans must have the executeOperation function this is what tests to see if the function will revert or no. Money must be sent back within the same transaction. Other note be careful when working with other contracts and fund it is important that you give them approval to move your funds. I had trouble figuring out why I could not interact with a governance contract and this was it. 
```
// SPDX-License-Identifier: MIT
pragma solidity 0.7.5;

import "./Govern.sol";
import "./ILendingPool.sol";

contract FlashVoter {
    ILendingPool constant pool = ILendingPool(0x7d2768dE32b0b80b7a3454c06BdAc94A69DDc7A9);
    IERC20 constant DAI = IERC20(0x6B175474E89094C44Da98b954EedeAC495271d0F);

    uint constant borrowAmount = 100000e18;

    Govern public governanceToken;
    uint public proposalId;

    constructor(Govern _governanceToken, uint _proposalId) {
        governanceToken = _governanceToken;
        proposalId = _proposalId;
    }

    function flashVote() external {
        address[] memory assets = new address[](1);
        assets[0] = address(DAI);
        uint[] memory amounts = new uint[](1);
        amounts[0] = borrowAmount;
        uint[] memory temp = new uint[](1);
        temp[0] = 0;
        pool.flashLoan(address(this), assets, amounts, temp, address(this), "", 0);
        
        
    }

    function executeOperation(
        address[] calldata,
        uint256[] calldata amounts,
        uint256[] calldata premiums,
        address, bytes calldata
    ) external returns(bool) {
        DAI.approve(address(governanceToken), amounts[0]);
        governanceToken.buy(amounts[0]);
        governanceToken.vote(proposalId, true);
        governanceToken.sell(amounts[0]);
        DAI.approve(address(pool), (amounts[0] + premiums[0]));
        
        return true;
    }
}
```
Governance Token used above:  
```
// SPDX-License-Identifier: MIT
pragma solidity 0.7.5;

import "./ERC20.sol";

contract Govern is ERC20 {
    IERC20 constant DAI = IERC20(0x6B175474E89094C44Da98b954EedeAC495271d0F);
    mapping(address => bool) hasVoted;

    struct Proposal {
        uint yesCount;
        uint noCount;
        mapping(address => bool) hasVoted;
    }
    
    uint numProposals;
    mapping(uint => Proposal) public proposals;

    constructor() ERC20("Govern", "GOV") {}
    
    function buy(uint _amount) external {
        DAI.transferFrom(msg.sender, address(this), _amount);
        _mint(msg.sender, _amount);
    }

    function sell(uint _amount) external {
        _burn(msg.sender, _amount);
        DAI.transfer(msg.sender, _amount);
    }

    function vote(uint _proposalId, bool _supports) external {
        require(!hasVoted[msg.sender]);
        Proposal storage proposal = proposals[_proposalId];

        if(_supports) {
            proposal.yesCount += balanceOf(msg.sender);
        } else {
            proposal.noCount += balanceOf(msg.sender);
        }

        proposal.hasVoted[msg.sender] = _supports;
    }
}
```
Note: Below is an example of why you need to be careful use AAVE as its possible to fake a lending pool. A lot of this is still difficult for me to understand but I want to note the delecall function allowing us to pass a call to another contract. While this is not good practice at all to use there may be some interesting use cases for it. 
```
//SPDX-License-Identifier: MIT
pragma solidity ^0.7.5;

interface IPool {
  function initialize(address) external;
}

contract Contract {
  IPool pool = IPool(0x987115C38Fd9Fd2aA2c6F1718451D167c13a3186);

  constructor() {
    pool.initialize(address(this));
    
  }

  function getLendingPoolCollateralManager() external view returns (address) {
    return address(this);
  }

  function liquidationCall(address,address,address,uint256,bool) external returns(uint, string memory) {
    address(0x5FbDB2315678afecb367f032d93F642f64180aa3).delegatecall(abi.encodeWithSignature("destruct()", "MyName"));
  }
}

// deployed @ 0x5FbDB2315678afecb367f032d93F642f64180aa3
contract Destructor {
  function destruct() external{
    selfdestruct(msg.sender);
  }   
}
```