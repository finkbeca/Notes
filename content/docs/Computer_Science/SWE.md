---
title: "Software Engineering"
weight: 1
bookFlatSection: false
bookToc: true
bookHidden: false
bookCollapseSection: false
#bookComments: false
---

# Notes from EECS 481

## Lecture 2 ~ Process, Risk and scheduling (1/10)
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-02-risk.pdf)  
### High Level
--- 
- Software Development process organizes, activities into distinct phases, 9design, coding, test, etc). Processes can increase efficiency, but are often implemented poorly  
- Effort estimation is based on historical information. It is complicated by uncertainty, which stems from risk, which can be managed. A project plan includes all of these considerations measuring progress is difficult!  

### Process
---
- A software development process or a software development life cycle or model divides software development into distinct phases to improve design, product, and project management  

- Process is the set of activities and associated with results that produce software  

Examples 
1.  Waterfall  
2. Agile   
3. Spiral Development  
4. Extreme Programming  

- Waterfall Method: Iterative phases carried out in order. 1. System and software requirements. 2. Analysis. 3. Design 4. Coding 5. Testing 6. Operations  
- Spiral Development Model focuses on the construction of an increasingly complete series of prototypes while accounting for risk.

### Process Issues and outcomes 
--- 
- Requirements: Infomal agreement changes {{<katex>}} \to {{</katex>}} Project scope expands  
- QA: Late detection of design and requirement issues, {{<katex>}} \to {{</katex>}} release with known defects  
- Defect tracking: informal bug reports {{<katex>}} \to {{</katex>}} bugs forgotten  
- System integration: Integration of independelty developed components at the very end of a project {{<katex>}} \to {{</katex>}} interface out of sync  
- Source Code Control: Accidentally overwritten changes {{<katex>}} \to {{</katex>}} lost work  
- Scheduling: project is behind, weekly new estimates, {{<katex>}} \to {{</katex>}} projects fall further behind.  

### Process Hypothesis  
---
- A process can increase flexibility and efficiency for software development  
- A repair cost is significantly more expensive post release then during coding or even at build time.  

### Estimation  
---
- Constructive cost model (cocomo) is a predictive model of time costs based on project history.  

### Risk and Uncertainty
---
- Risk management is the identification assessment and prioritization of risks, followed by efforts to minimize, monitor and control unseen events and outcomes.  

### Difficulties in software planning    
- Intangible results, mean progress may be hard to measure.    
- Software projects tend to fail more often as they are typically innovative.   
### Milestones and Deliverables    
- A milestone is a clenn end point of a (sub)task, often used by PMs, can be considered prototypes, MVPs, reports, etc   
- Deliverable are results for the customer, outward facing.  

## Lecture 3 ~ Measurement (1/12)
---
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-03-measure.pdf)  
### Overview  
---
- Software metrics are widely used in industry to spport deision making. Metrics are often inadequately supported and thus lack validity. Use carefully!
- Measurement is a fundamental activity but is influenced by human biases. Easy to misinterpret and to focus on what is easy to measure. Metrics can incentivize perverse behavior.
- Managers are often concerned with real world metrics than individual metrics
### Maintainability Index
---
- Maintainability index calculates an index values in the range (0,100) that represents the relative ease of maintaining the code. A high value means better maintainability. Ratings are often color coded with a green rating being between (20,100), yellow rating (10,19), and a red rating between (0,9).  Maintainability Index = (0, (171 - 5.2 * log(Halstead Volume) - 0.23 * (Cyclomatic Complexity) - 16.2 * log(Lines of code)) * 100 /171)
- Common practice when measuring lines of code is to ignore comments and empty lines, ignore lines with fewer than 2 characters and pretty print source code first. Also normalized across language code is written in.
- Halstead Volume = number of operators / operands * log2(number of distinct operators / operator), this is used to approximate the size of elements and the vocabulary.
- Cyclomatic complexity is based on control flow graphs and it measures linearly independent paths through a program
### Software Quality Metric  
---
- A software quality metric is a function whose inputs are software data and whose output is a single numerical value that can be interpretted as the degree tto which a software possesses a given attribute that effects quality  
Examples:  
1. Security  
2. Scalability  
3. Ease of use
4. Maintainability
5. Privacy
6. Performance

- The streetlight effect is a type of observational bias that occurs when people are searching for something and look only where it is easiest.  

### Dangers when using metrics
---
- Bad statistics  
- Bad decisions, incorrect use of the measurement  
- Bad incentives, disregard for human factors  
- False positive paradox is a stats result where false positive tests are more probable then true positive tets, occurring when the overall population has a low incidence of a condition and the incidence rate is lower than the false positive rate.
### Measurement scales
---
- Scale the type of data being measured, options include nominal (catergories), ordinal (order), interval (order, magnitude, but not zero), ratio, absolute
### Confounds in Software Analysis
---
- McNamara fallacy involes making a decision only based on quantitative data and ignoring all other observations. 

## Lecture 4 ~ Quality Assurance and testing (1/19)
---
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-04-qatesting.pdf)  
### Overview
---
- Quality Assurance(QA) maintains desired product properties through process choices  
- Testing: involves running the program and inspecting its results or behavior. It is the dominant approach to software QA. Types of tests include regression testing, unit testing, and integration testing.
- Mocking uses simple replacement functionality to test difficult, expensive, modules or features.  
### QA
---
QA is the maintenance of a desired level of quality in a service or product especially by means of attention to every stage of the process of delivery or production.
- External motivation for QA is that a program should do the write thing  
- Internal motivation for QA is that a program should be readable, maintainable, etc.  
- Maintainability is one of the most important aspects of internal QA motivation!  
- External QA motivations are to mitigate security issues, crashing, privacy breaches, etc.  

- There is no one solution to make sure a piece of software is correct, we've shown this via the halting problem.  

### Testing  
---
- Software testing is an investigation conducted to provide stakeholders with information about the quality of software. Involes typically data and a comparison of the output. Testing gives you confidence that your implementation adheres to your spec.
Testing types:  
1. Fuzz testing (testing with random inputs)
2. Regression testing
3. Unit Testing
4. Xunit
5. Integration testing
6. Mocking

### Regression Testing
---
- A test made after a bug is fixed to help mitigate the chance of having that bug again, when you fix a bug, add a test case that exposes that bug specifically.  
### Unit Testing
---
- Unit testing: individual units of source code, sets of one or more modules together are tested to determine whether they are fit for use.  
- Modern frameworks are collectively referred to as xUnit.  
- XUnit Features: 1. Tests cases, looks likes other code. 2. a test case discovered finds all such tests 3. A test case runner chooses which tests to run
- A test fixture is a specific piece of code to be run before after each test case
- A unit test features in isolation
- Unit tests tests are small and fast.
### Test-Driven Development
---
Test-driven development is a software development process that relies on the repetition of a very short development cycle: requirements are turned into specific test cases, then the software is improved so that the tests pass.
- Integration testing combines and tests individual modules as groups.

### Mocking
---
-Some languages provide dynamic mocking libraries that allow you to substitute objects and functions at runtime. Substitutes some function call or api call for a fixed values, allows for early stage development to still have robust  testings and helps test high cost functionality.
- Dynamic mocking requires good integration tests, but generally test cases with mocking are incredibly fragile.

## Lecture 5 ~ Test Suite Quality Metrics (1/24)
---
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-05-testquality.pdf)

### Overview
---
- Test Suite quality metrics help us decide which suite to use  
- Line coverage is the fraction of lines visited when running a suite  
- Branch coverage requires both true and false values for conditions, it is seem as a richer metric.  
- Mutation analysis measures the fraction of seeded defects detected by a suite, it is expensive but effective.
- Beta and A/B testing involve real users and their experiences.
### Review
---
- Testing is the most common dynamic technique for software QA
- Testing is very expensive, but poor tests, or no tests are more expensive.
### Lens of Logic
---
- How do we make sure we are testing in an effective manner?  
- Informal Desideratum. The program passes the tests if and only if it does all the right things and none of the wrong things
- X coverage means the degree to which X is executed/ exercised by a test suite
- Outside of industries (aerospace), formal traceability between requirements and tests cases (each test case would have an annotation ) saying passing X requires Y  
- You should assume that generally there is no formal traceability.  
- It is generally easier to test on bad things,then to check for good things, let us construct tests that validate if our program does not do certain bad things.
- If we never test a line X then testing cannot rule out the presence of a bug on Line X.
- When we do comparisons note that we might use AOTBE (All other things being equal), in such a case we assume such, and only consider defined differences.
- Simplying Assumptions: We gain the same amount of information of confidence for each visited line. Assumption 2, the amount of confidecne we gain per visted line is positive. 
- Test suite quality metric or test suite adequacy criterion assesses the quality of a test suite  
- Line coverage is a test suite quality metric: it is the number of unique lines visted by a program when running the test suite.  
- Coverage is a metric that allows us to compare two test suites and pick the better one  
- This information can then be used to guide decision making in software processes.  
- Observer Effect is the fact that simply observing a situation or phenomenon necessarily changes that phenomenon  
- Coverage instrumentation modifies a program to record coverage information in a way that minimizes the observer effect.
- Problems with line coverage? Statement coverage is lacking.  
- data values cause implicit or explicit changes of control and thus they cause different branches of conditionals to execute.  
- Branch coverage is a test suite quality metric that counts the total number of conditional branches exercised by that test suite. Branch coverage can generally subsume line coverage, and generally gives us more confidence than line coverage.
- Branch coverage is more expensive, as it is harder for a test suite to have high branch coverage than to have line coverage
- Function coverage: what fraction of functions have been called?  
- Condition coverage: What fraction of boolean subexpressions have been evaluated to both true and false.
- Function coverage + branch coverage
### Lens of Statistics
---
- The bugs experienced by users are the one that matter, and bugs that are not don't matter. 
- Assuming that user experience bugs are the ones that matter, testing should be devoted to sampling those inputs that users will provide  This could be done by sampling what users do most, or what causes users the most harm.  
- Sampling error is incurred when the statistical characteristics of a population are estimated from a subset, or sample, of that population. 
- Testing gives confidence the same way sampling (polling) gives confidence.  
- Sampling bias is a bias in which a sample is collected in such a way that some members of the intended population are less likely to be included than others.   
- In statistics, there is usually assumptions that we need to make about the underlyinng statistics, however in SE we do not know this distribution. 
**Alpha Beta Testing** 
- Alpha testing is done by developers  
- Beta testing is testing done by external users  
- Alpha, Beta testing can be viewed as directly sampling the space of user inputs.
---
- A/B testing involves two variants of your software A, B which differ only in one feature. Different users are shown different variants and responses are recorded, the better instance is then chosen going forward.  
- Sampling what users do most is sometimes called workload generation
### Lens of Adversity
---
- Mutation testing is a test suite adequacy metric in which the quality of a test is related to the number of intentionally added defects it finds.  
- Defect seeding is the process of intentionally introducing a defect into a program. The defect introduced is typicall intentionally similar to defects introducted by real developers.
- Mutation operator systematically changes a program point, in mutation testing the operators are modeled on historic human defects. 
- A mutant is a version of the original program produced by applying one or more mutation operators to one or more program locations. The order of a mutant is the number of mutation operators applied. 
- The Competent programmer hypothesis holds that program faults are syntactically small and can be corrected with a few key strokes. 
- The coupling effect hypothesis holds that complex faults are "coupled" with simple faults, such that a test suite that detects all simple faults will detect a high percentage of complex faults   
- A test suite is said to kill a mutant if the mutant fails a test that the original has passed.  
- Mutation testing of a test suite proceeds by making a number of mutants and measuring the fraction of them killed by that test suite. This fraction is called the mutation adequacy score or mutations core.  
- Note that are some programs that can be mutants, but are actually semantically equivalent to the original. Detecting these mutants are a big deal! In fact it is undecidable. 




## Lecture 6 ~ Quality Assurance and testing (1/19)
---
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-06-inputsoracles.pdf)

### Overview
---