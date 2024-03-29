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




## Lecture 6 ~ Inputs and Oracles (1/19)
---
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-06-inputsoracles.pdf)

### Overview
---
- A test case consists of an input (data), an oracle and a comparator.  
- Test inputs determine the behavior of the program. High coverage inputs can be generated automatically through path enumeration , path predicates, and mathematical constraint solving.
- Test oracles correspond to what the program should do. Generating them is an expensive problem; it can be done automatically through invariants and mutation.  
### Review
---
- Testing is very expensive  
- Test suite quality metrics support informed comparisons between tests.  
### Test inputs
---
- a test case has three components, the test input (data), the test oracle (expected output), and the comparator.
- Often time test cases are "much match exactly" but other more general comparators, like known random output, precision limits, embedded dates are possible  
- Examples of test inputs, are user input, GUI, environment variables, command line arguments, scheduler interleavings data from the filesystem, and data from the network.   
- Some systems like unix treat everything as a file, every thing even keyboard commands boil down to some special file.
- Programs interact with the outside world through system calls.  
### Test Input Generation
---
-  We want to generate high quality tests, automatically.
- Using test suite metrics to prefer some tests  
- Statement coverage: visit every line  
- Branch coverage: visit every -> true, -> false conditional
- Path coverage: visit every path  
- If we have N sequential if statements, we have 2N branch edges, but there are 2^N paths!!! Thus you would need 2^n tests to cover them Note that path coverage subsumes branch coverage.  
- A path predicated is a boolean formula over program variables that is true when the program executes the given path.  
- A satisfying assignment is a mapping from variables to values that make a predicate true.  
- How do we produce satisfying assignments? Guess randomly. Ask Humans, or use an automated theorem prover.  
- Input Generation plan: enumerator " all" paths in the method. For each path, collect the path predicate, for each path predicate, solve it. Note there could be infinite many paths in a solution thus be careful!
### Oracles
---
- The oracle problem is the difficulty and cost of determining the correct test oracle. The problem is expensive both for humans and for machines.  
- An implicit oracle is one associated with the language or architecture, rather than program-specific semantics.
### Invariants
- We can learn program invariants by running the program many times and noting what is always true of the output.  
- An invariant is a predicate over program expressions that is true on every execution.  
- An invariant or oracle captures human-intended correctness, there must be at least one line of code that ensures it. thus mutatnts in your program should be able to falsify the invariant.
---
Given a set of test cases and coverage information for each one, the test suite minimization problem is to find the minimal number of test cases that still have the max coverage.

## Lecture 7 ~ Code Inspection and Review (1/31)
---
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-07-codereview.pdf)
### Overview
---
- In a code review, another develop examines your proposed change and explanation, offers feedback, and decides whether to accept it.  
- A formal code inspection, a team of developers meets and examines existing code, following a process to understand it and spot issues.  
- Both of these static quality assurance approaches have costs and benefits.  
### Why not simply test?
- Faults can mask other faults at runtime  
- Only completed implementations can be tested  
- Many quality attributes (security, compliance, maintainability), are hard to test  
- Non-code artifacts cannot be tested.
### What to Examine
---
- Code Inspection: Examine whole program, expensive if the program changes, good if a new concern arises.  
- Code Review: Examine each change, inductive argument, bad if the definition of "good" changes.  
- Pull requests let you tell others about changes you pushed to a repo, once a pull request is open, you can discuss and review the potential changes with collaborators and add follow up commits before the changes are merged into the repo.  
- Other contributors can review your proposed changes, add review comments, contribute to the pull request discussion, and even add commits to the pull requests.

### Code Review Goals
- Finding defects, both low-level and high level issues  
- Code improvement, readability, formatting, commenting, consistency.
- Identifying alternative solutions  
- Knowledge transfer  
- Team awareness and transparency, lets others double check changes, and annouce changes to specific developers or the entire team.  
- Shared code ownership, openness toward critique and changes.
### Code Inspections
- In a formal code inspection a group of developers meets to review code or other artifacts. This is viewed as the most effective approach to finding bugs.  
- In a formal code inspection, there are typically 4-5 people, author, inspector, reader, scribe, and moderator.
- First a moderator is chosen, followed by an overview brief where an author presents context in meeting, next a preparation period where every reviewer inspects the code separately.  Next a meeting to discuss the code, have reviewers identify issues, meeting only discover issues, do not discuss solution or whether it really is an issue, followed by rework and maybe a follow-up.  
- What to look for: reminder of what to look for.  Author do not explain or defend the code, this isn't objective.  
- Meetings should not include management.  
- Do not use code reviews for HR evaluations. 
### When to inspect
- Inspect before milestones
- Incremental inspections during development, earlier often better than later.  
- Large code bases can be expensive and frustrating to review.  
### Guidelines for inspections
- Short meetings, not longer than 60 minutes.
- Schedule fewer than 400 LOC for a 1h review session. 
- Prep! More issues happen in the prep than the meeting itself. 
### Concluding thoughts
- Formal inspections are very expensive!
- Passaround review is distributed, asychronous.  
- Code reviews vs testing, code reviews are claimed to be more cost effective. 
### Code Review by formaility
- Ad hoc review  
- Passaround (modern code reviews)  
- Pair programming  
- Walkthrough  
- Inspection  
See slide attached above to see when to use each.
 ## Lecture 8 ~ Dynamic Analyses (2/2)
---
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-08-dynamic.pdf)
### Overview
--- 
- A dynamic analysis runs an instrumented program in a controlled manner to collect information which can be analyzed to learn about a property of interest.  
- Computing test coverage is a dynamic analysis. 
- Instrumentation can take the form of source code or binary rewriting.  
- Dynamic analysis limitations include efficiency, false positives, and false negatives. 
- May companies use dynamic analyses especially for hard to test bugs. 
---
- A race condition is the behavior of a system where the output is dependent on the sequence or timing of other uncontrollable events. In software, a race conditions occurs when two or more concurrent processes or threads access the same shared state without mutual exclusion and at least one of them writes to that state.    
### Common Dynamic Analyses
---
- Run the program, in a systematic manner, on controlled inputs, monitor internal state at runtime, instrument the program, capture data to learn more then pass/fail. Analyze the results.
- Instrumenting a program involves modifying or rewriting its source code or binary executable to change its behavior, typically to record additional information.
- Note, compile time and run time are not the same. Compile tile is preparing the program to record information while run time is actually recording said information.  
- Information flow tracking, sources are where sensitive information enters the program. Sinks are untrusted communication channels or sensitive computations.  
### Components of a Dynamic Analysis
---
- Property of interest, what are you trying to learn about? why?
- Information related to property of interest. How are you learning about that property.
- Mechanism for collecting that information from a program execution, how are we instrumenting it?  
- Test input data, what are you running the program on
- Mechanism for learning about the property of interest from the information you collected.  
- Example: Branch coverge is our test suite, and thus the property of interest, we care about what branch was exeucted, we let out a logging statement for each branch. In terms of learning from our collected data we use postprocess, discard duplicates, divide observed # by total.  
### Parsing and pretty printing
---
- parsing turns program text into an intermediate representation, pretty printing does the reverse. 
- Pretty printers are often written separately, visitors and pattern matchers exists in practice!  
### Cost and Limits
- Performance overhead for recording  
- Computational effort for analysis  
- Transparency limitations of instrumentation  
- Accuracy? False Positives/ False negatives. 
### Sound and Completeness
- Sound Analyses, if report all defects then there is no false negatives.
- Sound analyses typically overapproximate possible behavior.  
- Are "conservative" with respect to saftey, when in doubt say it is unsafe.  
- Complete analyses, every reported defect is an actual defect then no false positives
- Complete analyses typically underapproximates possible behavior. 



## Lecture 9 ~ Pair Programming (2/7)
---
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-20-pairskill.pdf)

### Overview
- There are many programming and development approaches for improving aspects of software development
- Agile development focuses on reducing the cost to respond to requirement change  
- Pair programming is a well-studied technique within Agile involving a driver and a navigator, it increases development time but decreases defect
- Skill based interviews help companies rule out poor-fit employees. They include both programming and behavioral questions. Interviewees should show and communicate all aspects of the software engineering process.  
---
### Common Threads
- Abstraction (inheritance, polymorphism), allows the same code to be applied to different data.  
- Modularity permits a separation of concerns, allowing code both sides of the interface to be changed independently.  
- Smaller work increments reduce the effort lost to, and minimize risk from changing requirements.  
- Smaller teams and customer involvement reduce risks from changing requirements and align software with stakeholders.
- Quality techniques (continuous integration, unit testing, pair programming, design patterns, refactoring, .etc) assure quality  
### Agile
- Agile is when the team requires relatively little time, cost, personnel, and resources to respond to a requirement change.  
- Team autonomy: the extent to which the software team has authority and control in making decisions to carry out the project.  
- Team diversity: the extent to which team members have different functional backgrounds, skills, expertise and experience.  
- There is little existing research that points to agile actually being better than other software development systems, it does offer a positive effect on response efficiency and a negative effect on response extensiveness. The team diversity typically has a positive effect on respond extensiveness. 
### Extreme Programming
- Extreme Programming (XP) is a software development methodology for improving software quality and responsiveness to changing customer requirements.   
- A type of agile software development
- Advocates frequent releases in short cycles
- Advocates pair programming, extensive code review, unit testing, code readability, etc
### Pair programming
- Pair programming refers to the practice whereby two programmers work together at one computer, collaborating on the same design, algorithm, code, or test.  
- The pair is made up a driver, who actively types at the computer or records a design, and a navigator who watches the work of the driver and attentively identififes problems, asks clarifying questions, and makes suggestions. Both are continuous brainstorming partners. 
- Results show that most professional programmers both enjoy collaborative programming more but also are more confident in their results. Though collaborative programming increases development cost by 15% to 100%, but reduces defects  and code size by 15%.
- Note tools like github copilot are not pair programming automation tools, but rather code synthesis and recommendation tools  
### CS Hiring Process
- 1-2 Phone screens, follows by an interview (most likely technical), followed sometimes by additional phone interviews. This ends with an offer if all goes well and this process typically last 2 weeks to 1.5 months.  
- Many companies avoid false positives at such a rate that they typically reject (false negatives) often.
- What is a good fit? Can you write and test code? Can you communicate CS concepts, are you a nice person?  
 ## Lecture 10-11 ~ Static and Dataflow analysis (2/9)
---
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-10-bugreport.pdf)

### Overview
- Static analysis is the systematic examination of an abstraction of program state space with respect to a property. Static analyses reason about all possible executions but they are conservative.  
- Dataflow analysis is a popular approach to static analysis. It tracks a few broad values rather than exact information. It can be computed in terms of a local transfer of information.  
---
### Fundamentals
- Abstraction capures semanitcally relevant details, elide other details, often handle the question of "I don't know" that comes up during development.  
- Program as Data. Programs are just trees, graphs or strings. And we know how to analyze and manipulate those!
- Some defects are very difficult to find via testing or manual inspections.
- Executing or dynamically analyzing all paths concretely to find such defects is not feasible. 
- Often want to learn about "all possible runs" of the program under a certain property.  
- Static analysis often finds defects that result from inconsistently following simple, mechanical design rules, Security, Memory, Resource leaks, API protocols, exceptions, encapsulation, data races.  
### Static Analysis
---
- Static analysis is the systematic examination of a n abstraction of program state space. (Static analyses do not execute the program!!!)  
- An Abstraction is a selective representation of the program that is simpler to analyze. 
-Analyses check if a particular property holds such as liveness (some good thing eventually happens), or safety (something bad never happens).
- An AST is a tree representation of the syntactic structure of source code. Records only semantically relevant information.
- AST treats program a s a tree, and treats a program as data. Note this relates to the idea of an universal turing machine. 
### Dataflow analysis
- Dataflow analysis is a technique for gathering information about the possible set of values calculated at various points in a program. We can abstract a program as an AST or a CFG. WE then abstract what we want to learn, and we finally give rules for computing those abstract values.  
-Correctness condition: On every path to the use of x, the last assignment to x is x:= 0  
-Shared traits among dataflow analyses: depends on knowing a property P at a particular point in program execution. Proving P at any point requires knowledge of an entire method body. Property P is typically undecidable.  
- Note we define that an Algorithm must always terminate. Thus a dataflow analysis algorithm must terminate even if the input program loops.
- Conservativeness: If the analysis depends on whether or not P is true, then want to know either P is definitely true, or we do not know what P  is.   
- In general we say it is always correct to say "don't know" all program analyses are conservative   
- We use an uppercase T denoted BT (bottom) to say a statement is not reachable, if we can definitively determine the value we give the value if the value cannot be determined, we call this T (top).  
***General Idea*** The analysis of a complicated program can be expressed as combination of simple rules relating the change in information between adjacent statements.  
- We briefly define a transfer function that transfers information from one statement to another.

### Rules for Dataflow Analysis  
1. C_O(x x:=c) = c, if c is constant  
2. C_O(x,s) = BT if C_I(x,s) = BT.
3. C_O(x, x:= f(...)) = T
4. C_O(x,y:= ... ) = C_I(x, y:= ...) if x != y 

The rules of 1-4 relate to the in and out of statements, In the following rules, let statement s have immediate predecssor statements p_1, ...P_n
5. C_O(x, p_i) = T for some i, then C_I(x,s) = T  
6. C_O(x, p_i) = c and C_O(x,  p_j) = d and d != c then C_I(x,s) = T 
7. if C_O(x,p_i)= c or BT for all i then C_I(x,s) = c  
8. if C_O(x,p_i) = BT for all i, then C_I(x,s) = BT  
- For every entry s to the program, set C_I(x,s) = T  
- Set C_I(x,s) = C_O(x,s) = BT everywhere else
- Repeat until all points satisfy rules 1-8. 
- The initial value BT means 'we have not yet analyzed control reaching this point', because of cycles, all points must have values at all times during the analysis. Intuitively assigning some initial value allows the analysis to break cycles.   
- We can order our values as BT < c < T  
### Secure Information  
- A variable x at stmt s is a possible sensitive information leak if there exists a statement s' that uses x, there is a path from s to s', that path has no intervening low security assignment to x.  
- H_i(x,s)= true if s displays x publicly true means 'if this ends up being a secret variable then we have a bug'
- H_i(x, x:= e) = false (any subsequent use is safe)  
- H_i(x,s) = H_o(x,s) if s does not refer to x
- H_out(x,p) = \lor { H_i(x,s) | s a successor of p} (if there is even one way to potentially have a leak we potentially have a leak).  
- H_i(y,x:=y) = H-O(x, x:=y)
- Algorithm: Let all H_(...) = false initially, repeat process until all statements s satisfy rules 1-4: pick s where one of 1-4 does not hold and update using the appropriate rule.
- A value can change from false to true, but no the other way around.  
- Each value can change ony once so termination is guaranteed.  
- Once the analysis is computed, it is simple to issue a warning at a particular entry point for sensitive information.  

## Lecture 12 - Defect Reporting and Triage (2/12)
---
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-10-bugreport.pdf)
### Overview
- A software defect report includes information and communication relate to addressing a software issue. Defects reports have many components.  
- Defect reports are subject to triage based on severity and priority information.  
- Defects reports have a lifecycle that is complicated and non-linear with multiple possible resolutions.  
### Terminology
- A fault is an exceptional situation at run time (trap, exception)  
- A defect is any characteristic of a product which hinders its usability for its intended purpose.  (a bug is a static defect in the source code).  
- A bug report provides information about a defect, created by testers, users, tools, etc. Often contains multiple types of information, often tracked in a database. 
- A feature request is a potential change to the intended purpose of software  
- AN issue is either a bug report  or a feature request.  
- Defect report lifecycle consists of a number of possible stages and actions including reporting, confirmation, triage, assignment, resolution, and verifcation.  
- The status of a defect report tracks its position in the lifecycle  
### Examples
- Bugzilla
- github built in issue tracker
### Bug Report Sources
- Internal, (Devs, Testers, reports are usually detailed and sophisticated )
- External (Beta testers, and end users), reports are usually more general.  
### Bug Triage
- Can be thought of as what bugs should be dealth with first.  
- Medically,  triage is the assignment of degrees of urgency to wounds or illnesses to decide the order of treatment of a large number of patients or casualities.  
- This is often due through cost-benefit analysis.  
- Severity is the degree of impact that a defect has on the development or operation of a component or system.  
- Defect priority indicates the importance or urgency of fixing a defect. 
- Note Severity and Priority are often correlated but are officially independent , severity and priority are used together to evaluated prioritize and assign the resolution of reports.   
- An assignment associates a developer with the responsibility of addressing a defect report, this is most often a manual process done by the 'owner' of the implicated code.  
- A defect report resolution status indicates the result of the most recent attempt to address it.  

## Lecture 13 - Fault Localization and Profiling
--- 
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-11-faultloc.pdf)  
###
- Debugger helps to detect the source of a program error by single stepping through the program and inspecting variable values.  
- Fault localization is the task of identifying lines implicated in a bug. Humans are better at localizing some types of bugs than others.  
- Automatic tools can help with the dynamic analyses of fault localization and profiling  
- Care must be taken when evaluating such tools for real-world use.  
### Software Scaling  
- Fault localization is the task of identifying source code regions implicated in a bug  
- There are many places to fix a bug, might be looked upon by supsiciousness, eg a list.   
### Debuggers
- Can operate on source code or assembly code  
- Inspect the values of registers, memory  
- Key Features: Attach to process, single stepping, breakpoints, conditional breakpoints, watchpoints  
### Signals
- Signal is an asynchronous notification sent to a process about an event  
- You can install a signal handler, a procedure that will be execute when the signal occurs.   
- Attaching a debugger requires operating system support.  
- There is a special system call that allows one process to act as a debugger for a target  
### Building a debugger
- A single step interactive command is equal to putting a breakpoint at the next instruction, resume execution...  
- A watchpoint is like a breakpoint but stops execution after any instruction changes the value at L.  
- Software and Hardware watchpoints implemented slightly different. (Both not optimal)  
### Tools
- A spectrum based fault localization tool uses a dynamic analysis to rank suspicious statements implicated in a fault by comparing the statements covered on failing tests to the statements covered on passing tests.  
- Print-Statement debugging
- A profile is a performance analysis tool that measures the frequency and duration of function calls as a program runs
- A flat profile computes the average call times for functions but does not break times down based on context  
- A call-graph profile computes call times for functions and also the call chains involved.  

## Lecture 14 - Debugging as Hypothesis Testing
--- 
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-12-debug.pdf)  
###
- Delta debugging is an automated debugging approach that finds a minimal interesting subset of a given set. It is very efficient.  
- Delta Debugging is based on divide and conquer and relies heavily on critical assumptions and consistency.    
- It can be used to find which code changes cause a bug to minimize failure inducing inputs and even to find harmful thread schedules.   
### Delta Debugging
- Problems: Simplifying failure inducing input, isolating failure inducing thread schedules, identifying failure inducing code changes.  
- Difference is a change in the program configuration or state that lead to alternate observations  
- Abstract Debugging problem: Find which part of something determines the failure, find the smallest subset of a given set that is still interesting, under some notion of "interesting" that is monotonic, unambiguous and consistent. 
- If a single changes induces the failure, DD is logarithmic in time, elsewise it is linear. 
- Reference slide deck above for more information.  

## Lecture 15 - Requirements and Specification
--- 
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-13-req.pdf)  
###
- Requirements articulate the relationship and interface between a desired system and its environment. This includes both what is and what should be.  
- We distinguish between functional and quality requirements. Both should be stated in measurable ways.    
- Requirements can describe variables, inputs, outputs, and assumptions between them.    
- We distinguish between informal statements and verifiable requirements.  
###
- Requirements say what the system will do, not how it will do it.  
- System requirements: relationships between monitored and controlled variables.  
- Software requirements: relationship between inputs and outputs.  
Domain properties and assumptions state relationships between those.  
- Requirements describe what is observable at the environment machine interface. 
- Indicative mood describes the environment (as-is)  
- Optative mood to describe the environment with the machine.  
### Functional Requirements
- Functional requirements describe what the machine should do, input, output, interface, response to events.   
- Completeness: All requirements are documented.  
- Consistency: No conflicts between requirements.  
- Precision: No ambiguity in requirements.  
- Think of quality requirements as a design criteria to help choose between alternative implementations.  
- An informal goal is a general intention  
- A verifiable non-functional requirement is a statement using some measure that can be objectively tested. 
### Requirements Engineering  
- Knowledge acquisition: how to capture relevant detail about a system.  
- Knowledge representation: once capture how do we express it most effectively. 

## Lecture 16 - Requirements Validation and Risk
--- 
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-13-req.pdf)  
###
- Requirements elicitation relies on communication with stakeholders. This includes identifying relevant parties, understanding the domain, interviews, and the exploration of alternatives.  
- Validation checks the correctness of requirements; verification checks the correctness of software.  
- Risk includes both the likelihood and the consequences of failure. 
### Requirement Elicitation
- Requirements elicitation is the process of identifying system requirements through communication with stakeholders, Step 1 identify stakeholders, 2. understand the domain, 3. discover the real needs.   
- A stakeholder is any person or group who will be affected by the system directly or indirectly.  
- Content analysis involves learning about the system domain. 
- Discover real needs via Interviews, conduct an interview, structure or unstructured, individual or group. 
### Inconsistencies
- Terminology clash same concept named differently
- Designation clash: same name for different concepts in different statements  
- Structure clash: same concept structured differently in different statements.  
- In a strong conflict statements are not satisfiable together  
- In a weak conflict statements are not satisfiable together under some boundary condition.  
- Alternative solutions and tradeoffs are typically presented via prototypes, mockups, and storyboards.  
### Verification and Validation  
- Validation is the task of determining if the requirements are correct.  
- Verification is the task of determining if the software is correct.  
- We recursively decompose a system, from the highest level of abstraction into lower-levels subsystems and implementation chocies.  
### Risk
- Risk = Likelihood \cdot Impact  
- Fault tree analysis is a top down technique to model, reason about, and analyze risk. A fault tree analysis decomposes a particular type of failure. 
## Lecture 17 - Design for Maintainability
--- 
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-17-designmaint.pdf)  
###
- Invest up front effort into designing software to facilitate maintenance activities. Reduces overall lifecycle costs. 
- Designing to improve comprehension, documentation, change, reuse, and testability. 
- The metrics used for understandability, the category of information conveyed by documentation, object oriented principles and design patterns.   
### Investment
- To invest is to allocated money in the expectation of some benefit in the future. 
- Investment is maintenance.  
- Readability is a human judgement of how easy a text is to read. 
### Descriptive vs Prescriptive  
- Descriptive modeling is a mathematical process that describes real-world events and the relationships between factors correlated with them.  
- Prescriptive model evaluates alternative solutions to answer the question according to an assumption or standard. 
- You should focus on adding why information to your documentation, comments, and commits. There is tool and process support for adding and recovering what information.  
### Design for change
- Many fundamental tenets of object oriented design facilitate subsequent change. 
- Classes are open for extension and modification.  
- Subtype polymorphism enables changes behind interfaces.  
- Classes encapsulate details likely to change behind stable interfaces.  
- Internal parts can be developed independently  
- Delegation is when one object relies on another object for some subset of its functionality.  
- A software design pattern is a general reusable solution to a commonly occurring problem within a given context. 
### Design Patterns
- Strategy Design Pattern.  
- Template Method 
- Template method uses inheritance + an overridable method, strategy uses an interface and polymorphism.  
### Design for Extensibility 
- Design by contract prescribes that software designers should define formal precise and verifiable interface specification for components.  

## Lecture 18 - Patterns and Anti-Patterns
--- 
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-16-patterns.pdf)  
###
- Software Design patterns are general reusable solutions to commonly occurring problems. They separate the structure of a system from its implementation. 
- Every design has tradeoffs no is perfect. 
- Gang of 4 = Design Patterns Elements of Reusable object-oriented software. 
### High Level Design Pattern Advice
- Consider Code changes as a certainity  
- Consider your requirements and their changes.  
- Consider multiple designs  
### Structural Patterns
- Structural design patterns ease design by identifying simple ways to realize relationships among entities.  
- Adapter design pattern is a structural design pattern that converts the interface of a class into another interface clients expect
- Composite design pattern allows clients to treat individual objects and groups of objects uniformly
- THe proxy design pattern provides a surrogate or placeholder for another object to control access to it.
### Creational Design Patterns
- Creational design patterns avoid complexity by controlling object creation so that objects are created in a manner suitable for the situation. 
- Named constructor idiom, you declare the class's normal constructors to be private or protected and make a public static creation method.   
- The factory method pattern is a creational design patter that uses factory methods to create objects without having the return type reveal the exact subclass.   
- Anti-pattern is a common response to a recurring problem that is usally ineffective and risk being counterproductive. 
- Singleton pattern restricts the instantiation of a class to exactly one logical instance. 
### Behavioral Design Patterns
- Behavioral design patterns support common communication patterns among objects. They are concerned with algorithms and the assignment of responsibilities.  
- Iterator pattern is a common behavioral design pattern, it provides a uniform interface for traversing containers. 
- Observer pattern allows depdent objects to be notified automatically when the state of a subject changes. 
- Template method design involves a method in a superclass that operates in terms of high level steps that are implemented by abstract helper methods provided by concrete implementations. 

## Lecture 18 - Multi-Language Projects
--- 
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-23-multilang.pdf)  
###
- Many modern projects involve code in many languages  
- Native code interfaces can be understood in terms of data layout and special common functions to manipulate managed data.
- Almost all aspects of modern SWE is multi-language!  
### Traditional Multi-Language Projects (MuL)
- Application kernel  
- Scripts  
- Retro64 Minecraft Mod
- Common language runtime
### Disadvantages of MuL Projects
- Integrating data and control flow across languages can be difficult
- Debugging can be hard  
- Build process becomes more complicated. 
- Developer expertise in multiple languages.
### Python
-Most Objects in python are just dictionaries.
- Different then C++ and Java
### Programming Paradigms
- Pass a string or an integer as a second argument ideal works well for dynamic languages like python as well as functional languages, but not for OO languages. 
### Cross-Cutting Implications for SWE
- Hiriing and Expertise, you need developers with experience working with both languages together, per language experince may not be equal to this.  
- Code Inspection and Review, our traditional style of code inspection and review does not hold under MuL projects.  
- Design: designng the interface for cross-language is extremely error prone, and planning is necessary. 
- Design patterns can help!  
- Readability, the "glue" code is incredibly hard to decipher without familiarity, and thus special care needs to be used in formatting and making sure any code is written well.  
- Test input generation (most tools do not support test input generation across MuL projects)  
- Test coverage, outside of giant ecosystems coverage tools do NOT span languages.  
- Mutation analysis: Mutation tools are typically language specific.  
- Debugger tools can almost never help with Mul projects.
- Pick one language and debug within  
- Static analysis: Unless the tool supports both languages, it will only report tools in one language even if it is a MuL project.
- Why use MuL projects? If you want to mainly use a high level programming language for ease of reading and usability while taking advantage at some point of low level aspects of a kernel.
## Lecture 19 - Code Inspection and the brain
--- 
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-18-brain.pdf)  
###
- We can investigate neural correlations in SWE using medical imaging.  
- Top-down comprehension based on semantic cues is more efficient than bottom up comprehension   
- Neural representation and natural languages are distinct. Classifiers can distinguish them based solely on brain activity. 
### Code Review and Comprehension
- Developers spend more time understanding and comprehending code than any other activity.  
- Code review is a defacto standard.   
- Technology transfer involves turning a research idea into an effective product that is actually used.  
### FMRI
- FMRI is a non invasive technique for probing neubiological substrates of various functions and measuring the (blood oxygen level depedent ) 
- This magnetic difference between oxygen rich and poor blood can be detected by a magnetic resonance scanner. 
### Models of Code Comprehension
- Top down comprehension: refers to cognitive process in which experience and expectation and semantic cues guide the understanding of the code.  
- Bottom up comprehension refers to cognitive processes in which meaning is obtained from every individual statement and then synthesized into a holistic understanding.  
- Neural effciency is the phenomenon where lower brain activation indicates that a cognitive process is more efficeint and thus seem as easier. 

### Study Results
- Comprehension based on semantic cues requires less cognitive effort than bottom up comprehension.  
- Program comprehension based on semantic cues is very efficient.  
## Lecture 20 - Productivity
--- 
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-19-productive.pdf)  
###
- Humans demonstrate different levels of expertise at programming tasks.
- We consider a number of hypothesis for why.  
- Organizations can provide hardware support. Individuals can practice abstractions and decompositions. 
### Rapid Response time
- The traditional model of a person thinking after each system response appears to be inaccurate. People have a sequence of actions in mind, contained in a short mental buffer.  
- A experienced engineer working with sub second response was as productive as an expert with slower response. A novice performance became as good as the experienced professional and productivity of an expert was dramatically enhanced.
### Programming Performance
- A significant performance factor is associated with faster coding / debugging time, less CPU time, and use the of a high order language.
- There is no correlation between grades and test scores in university and performance in the workplace.
- Substantial savings can be effected by successfully detecting low performers.
- From the Mythical Man we know on average 3 lines of code were added today, however on 10 lines can be added given a high order language like Python. (High order languages are effectively more efficient. ) This is otherwise known as language invariance.  
### Problem solving 
- They way experts vs novices solve problems tend to differ greatly besides more obvious differences like the number of commits made with errors.  
- Problem solving tend to be different between novices and experts, where expert are more dependent on surface features, whereas experts focus more on underlying principles.  
- With learning there is a gradual shift in organization of knowledge. From centering on physical components to one where there is a combined reliance on physical components, and physical laws, and finally one unrelated to any physical components.   

## Lecture 21 - Automated Program Repair
--- 
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-24-repair.pdf)  
### Bug Bounties
- If you trust your triage and code review, anyone can submit a candidate bug report (often time incentivize monetarily)  
- Bug bounties combine defect reporting and triage with pass-around code review.  
- With the high cost of QA paying for bug bounties is a very economical way to handle bug fixing. 
### Automatic Bug Repair
- Given a program and evidence of a bug, we can create a pull request that fixes a given bug!  
- How would this work? Fault localization can be used to minimize the area of the problem, this can typically be done within a range of 10-100 lines. Furthermore we can use mutation testing to generate a candidate from simple edits. We can then use regression testing and continuous integration to assess the quality this change.    
- Delta Debugging can be used to find a passing 1-minimal edit subset when minimizing edits.  
- The main cost of automated program repair is running tests, you should use test suite prioritization and minimizing the tests to reduce this. Furthermore, stop evaluating as soon as a single tests fail.  
- Static analysis can be used to decide if two programs are approximately equivalent. 
- Mutation testing typically takes a program that passes all of its test suite, and requires that mutants based on human mistakes from the entire program fail some test. In contrast, a program repair that a failing program and requires one mutant that repairs (passes all the test), where the mutant is located in the lines of code found via fault localization.  
- Dynamic analysis can be used to detect concurrency bugs.  
- Automated test repair is relatively cheap compared to human developers, a useful tool for simple bugs, leaving complex/creative fixes for human developers.  

## Lecture 22 - Product Management
--- 
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/shultz-pm.pdf)  
### Being a PM
- Product Manger/ Program Manager/ Project Managers. Subtly different but generally the same.   
- "PM are the voice of the customer for product development", "PMs make sure companies build the right things, and SWE make sure these things are built right".  
- "PM's help understand and prototype"  
- Often ambiguous, and generally lack control over the product, they must influence without authority.  
### What does it take to a be a good PM
- Ship the improvement
- Show a tangigble difference in an important metric
- get promoted
- think up and implement diagnostics to prevent support cases  
- see support case result time for common issues go down  
- Relates to elicitation, validation, and risk. (Talking with customers, and making sure you understand the root of their pain)
- Relates to system design, mapping users needs into a technical design. 
- How to communicate: Communicate yours needs as directly as possible, put your best foot forward, work earnestly to under other person's problems, escalate tell other people in authority what problems your face.
- If a sitaution is bad you don't have to try and resolve it.   
## Lecture 23 - Program Synthesis
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-program-synthesis.pdf)  
###
- Flash fill is one of the prime examples of program synthesis. 
- Flash fill has an underlying programming language. It is known as a domain specific language, a language specialized to some application domain.   
- As a DSL it can only perform computations in this language, it cannot synthesize programs that are not expressible in its underlying language. 
- Program synthesis is the process of taking some high level intent and translating it into some lower level code. 
- Program synthesis is not the same as a ML model, how we think about programs are very different, what they are trying to correlate is also different.  
- Likewise compilers are not the same as program synthesis. 
- Synthesis is part of a SDP, scalability will improve, looking to the future, we care more about making these synthesizers usable, and building out the interface to communicate with. 
--- 
## Lecture 24 - World Building
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/weimer-worldbuilding.pdf)  
###
- World building is the process of constructing an imaginary world. 
- In addition to aesthetics, we can use GNS theory, and psychographic profiles as lenses to examine user desires.   
- Give our desires, we can allocate resources to world building as well as mechanics and dynamics. 
- World building is not a Genre.  
- World building is the process of constructing an imaginary world. 
- world build is used to make developers and players happy.  
- GNS explains interactions through 3 mains catergories: gamists, narrativists, and simulationists. 
- Psychographic profiles, jonhnny make mechanics creative for self expression, timmy experience big dynamics, spike wants to win, vorthos wants to expereince the creative and flavor of the project.  
- World building can be considered both top-down or bottom up. Requires requirement elicitation just like SWE. 
- Careful balance is needed to between too much world building, and massive plot holes, furthermore world building is not everything other mechanics need to be built out too. 
- Can be thought of building out a process for creative works, design, and development. 
--- 


