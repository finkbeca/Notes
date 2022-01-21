---
title: "Software Engineering"
weight: 1
bookFlatSection: false
bookToc: true
bookHidden: false
bookCollapseSection: false
#bookComments: false
---

## Notes from EECS 481

### Lecture 2 ~ Process, Risk and scheduling (1/10)
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-02-risk.pdf)  
**High Level**
--- 
- Software Development process organizes, activities into distinct phases, 9design, coding, test, etc). Processes can increase efficiency, but are often implemented poorly  
- Effort estimation is based on historical information. It is complicated by uncertainty, which stems from risk, which can be managed. A project plan includes all of these considerations measuring progress is difficult!  

**Process**
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

**Process Issues and outcomes** 
--- 
- Requirements: Infomal agreement changes {{<katex>}} \to {{</katex>}} Project scope expands  
- QA: Late detection of design and requirement issues, {{<katex>}} \to {{</katex>}} release with known defects  
- Defect tracking: informal bug reports {{<katex>}} \to {{</katex>}} bugs forgotten  
- System integration: Integration of independelty developed components at the very end of a project {{<katex>}} \to {{</katex>}} interface out of sync  
- Source Code Control: Accidentally overwritten changes {{<katex>}} \to {{</katex>}} lost work  
- Scheduling: project is behind, weekly new estimates, {{<katex>}} \to {{</katex>}} projects fall further behind.  

**Process Hypothesis**  
---
- A process can increase flexibility and efficiency for software development  
- A repair cost is significantly more expensive post release then during coding or even at build time.  

**Estimation**  
---
- Constructive cost model (cocomo) is a predictive model of time costs based on project history.  

**Risk and Uncertainty**
---
- Risk management is the identification assessment and prioritization of risks, followed by efforts to minimize, monitor and control unseen events and outcomes.  

**Difficulties in software planning**    
- Intangible results, mean progress may be hard to measure.    
- Software projects tend to fail more often as they are typically innovative.    
**Milestones and Deliverables**    
- A milestone is a clenn end point of a (sub)task, often used by PMs, can be considered prototypes, MVPs, reports, etc   
- Deliverable are results for the customer, outward facing.  

### Lecture 3 ~ Measurement (1/12)
---
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-03-measure.pdf)  
**Overview**  
---
- Software metrics are widely used in industry to spport deision making. Metrics are often inadequately supported and thus lack validity. Use carefully!
- Measurement is a fundamental activity but is influenced by human biases. Easy to misinterpret and to focus on what is easy to measure. Metrics can incentivize perverse behavior.
- Managers are often concerned with real world metrics than individual metrics
**Maintainability Index**
---
- Maintainability index calculates an index values in the range (0,100) that represents the relative ease of maintaining the code. A high value means better maintainability. Ratings are often color coded with a green rating being between (20,100), yellow rating (10,19), and a red rating between (0,9).  Maintainability Index = (0, (171 - 5.2 * log(Halstead Volume) - 0.23 * (Cyclomatic Complexity) - 16.2 * log(Lines of code)) * 100 /171)
- Common practice when measuring lines of code is to ignore comments and empty lines, ignore lines with fewer than 2 characters and pretty print source code first. Also normalized across language code is written in.
- Halstead Volume = number of operators / operands * log2(number of distinct operators / operator), this is used to approximate the size of elements and the vocabulary.
- Cyclomatic complexity is based on control flow graphs and it measures linearly independent paths through a program
**Software Quality Metric**  
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

**Dangers when using metrics**
---
- Bad statistics  
- Bad decisions, incorrect use of the measurement  
- Bad incentives, disregard for human factors  
- False positive paradox is a stats result where false positive tests are more probable then true positive tets, occurring when the overall population has a low incidence of a condition and the incidence rate is lower than the false positive rate.
**Measurement scales**
---
- Scale the type of data being measured, options include nominal (catergories), ordinal (order), interval (order, magnitude, but not zero), ratio, absolute
**Confounds in Software Analysis**
---
-McNamara fallacy involes making a decision only based on quantitative data and ignoring all other observations. 

### Lecture 4 ~ Quality Assurance and testing (1/19)
---
[Slides](https://web.eecs.umich.edu/~weimerw/481/lectures/se-04-qatesting.pdf)  
**Overview**
---
- Quality Assurance(QA) maintains desired product properties through process choices  
- Testing: involves running the program and inspecting its results or behavior. It is the dominant approach to software QA. Types of tests include regression testing, unit testing, and integration testing.
- Mocking uses simple replacement functionality to test difficult, expensive, modules or features.  
**QA**
QA is the maintenance of a desired level of quality in a service or product especially by means of attention to every stage of the process of delivery or production.
- External motivation for QA is that a program should do the write thing  
- Internal motivation for QA is that a program should be readable, maintainable, etc.  
- Maintainability is one of the most important aspects of internal QA motivation!  
- External QA motivations are to mitigate security issues, crashing, privacy breaches, etc.  

- There is no one solution to make sure a piece of software is correct, we've shown this via the halting problem.  

**Testing**  
---
- Software testing is an investigation conducted to provide stakeholders with information about the quality of software. Involes typically data and a comparison of the output. Testing gives you confidence that your implementation adheres to your spec.
Testing types:  
1. Fuzz testing (testing with random inputs)
2. Regression testing
3. Unit Testing
4. Xunit
5. Integration testing
6. Mocking

**Regression Testing**
---
- A test made after a bug is fixed to help mitigate the chance of having that bug again, when you fix a bug, add a test case that exposes that bug specifically.  
**Unit Testing**
---
- Unit testing: individual units of source code, sets of one or more modules together are tested to determine whether they are fit for use.  
- Modern frameworks are collectively referred to as xUnit.  
- XUnit Features: 1. Tests cases, looks likes other code. 2. a test case discovered finds all such tests 3. A test case runner chooses which tests to run
- A test fixture is a specific piece of code to be run before after each test case
- A unit test features in isolation
- Unit tests tests are small and fast.
**Test-Driven Development**
---
Test-driven development is a software development process that relies on the repetition of a very short development cycle: requirements are turned into specific test cases, then the software is improved so that the tests pass.
- Integration testing combines and tests individual modules as groups.

**Mocking**
-Some languages provide dynamic mocking libraries that allow you to substitute objects and functions at runtime. Substitutes some function call or api call for a fixed values, allows for early stage development to still have robust  testings and helps test high cost functionality.
- Dynamic mocking requires good integration tests, but generally test cases with mocking are incredibly fragile.

