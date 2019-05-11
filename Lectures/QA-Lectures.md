# 3 Introduction to Software Development and Testing
- 3 вида software - Retail | Web | Mobile




# 4 Test cases, test scenarios, test execution. 

## What is SRS?
A software requirements specification (SRS) is a description of a software system to be developed, laying out functional and non-functional requirements, and may include a set of use cases that describe interactions the users will have with the software.

## Requirements
Establishes the basic agreement between costumer and contractor
- What software product to do
- What is NOT expected to do
- Should enlist enough and necessary requirements for the project development
- Should have clear understanding of the product
- Often changed after each meeting with customer

## Use Cases
- List of interaction steps
- Defines relation between an actor and a system
- Usually satisfying a goal
- Actors are able to take decisions
- Decisions lead to subcases

==> Models
- Can be modeled via UML (
- Can be flat text documents

==> Template
- Name
- Actors
- Preconditions
- Flow
- Post conditions


## Readability
In order to be easy to read, an SRS should answer:
- Contains a high-level description of the scope?
- Is it easy to navigate?
- Is it easy to distinct primary from secondary cases?
- Contains links to related features?
- Calls out questions which still need to be addressed?

## Review

SRS review is going to through the document and trying to understand what the target application is going to be like. 
The review results in:
- Test scenarios list
- Found errors by statically going through the document
- Questions for better understanding
- Preliminary idea of the test environment
- Test scope identification
- How many test cases will end-up having




# 5 Test Levels and Test Types
Functional and Non-Functional testing

## Test Levels
==> Component Testing: Unit tests focus on aspects internal to the component itself.

    --> Testing separate components/units of the software. 
    --> Software units (components): Modules, units, programs, functions, Classes – in Object Oriented Programming
    --> Individual testing: Components are tested individually and Isolated from all other software components
    --> Isolation - Prevents external influences on the components. Interaction with neighbors is not performed


==> Integration Testing: Supposes that components are already tested individually

    --> System integration testing: Testing the integration of systems and packages
    --> Testing interfaces to external organizations/3rd parties
    --> Expose defects in the interfaces and interaction between integrated components
    ===> The Big Bang approach: All components or modules are integrated simultaneously, after which everything is tested as a whole. Disadvantage: difficult to trace the cause of failures
    
    ===> The Incremental approach: All components are integrated one by one and a testing is carried out after each step.
    Different Incremental approaches:
        - The Top-Down approach: The high level logic and flows are tested first - the low level components are tested last.
        - The Bottom-Up approach: The most complex / high level functionalities are tested last.


==> System Testing: 

    --> In System testing the behavior of the whole system/product is tested as defined by the SRS. 
    --> Is a higher level testing than the Unit and Integration testing. 
    --> Test the system from the perspective of the end user / customer.
    --> Performed by testers.


==> Acceptance Testing

    --> Also known as User Acceptance Testing (UAT).
    --> The End user / Customer is actually involved in the testing.
    --> Performed on a production like environment.

## Test Types
==> Structural testing

    Often referred to as ‘white-box’ or ‘glass-box’ testing. Uses information about the internal code structure or architecture.
    Tools can be used to measure the code coverage of elements, such as Statements or Decisions / Branches.

==> Change related testing

    --> Re-testing: 
    After a bug has been detected and fixed, the software should be re-tested. To confirm that the original defect has been successfully removed after applying the fix. Also known as Confirmation testing.
    
    --> Regression Testing:
    Performed after modifications of the code. Testing for newly introduced faults as a result of the changes made to the system.
    May be performed at all test levels. The reason for Regression testing is that changed or new code might affect untouched functionalities.
    Testing only code, that is changed, is not enough!

==> Risk-Based Testing

    Prioritization Of Tests Based On Risk And Cost. Two main types of risk:
    = Product (quality) risks - The primary effect of a potential problem is on the product quality.
    = Project (planning) risks - The primary effect is on the project success.

==> Functional Testing

    Functional testing verifies the system's input–output behavior. Black box testing methods are used.
    The test cases are based on the functional requirements.
    The main goal is to exercise the functionality and verify the expected behavior.


==> Non-functional Testing

    Testing Non-functional Software Characteristics. “How well" the system should carry out its functions. Non-functional characteristics:
    --> Reliability
    --> Usability
    --> Accessibility
    --> Efficiency
    --> Security
    --> etc.
    
    --> Performance - speed, How fast is the system?
    The goal of performance testing is to:
    Determine compliance with performance goals and requirements
    Establish a baseline for future regression testing
    Eliminate bottlenecks


    --> Load - scalability, How much load can the system handle?
    Load Testing aims to identify the need of improving the applications:
    The best source of information during load tests are:
    = Average Response times
    = Peak Response times
    = Error Rates
    = Requests per second
    = Concurrent Users Count
    Performance: Do we need to reduce the time needed to execute a request ?
    Scalability: Can the system handle the anticipated number of concurrent users during peak load in production?
    Stability: Does the application suffer from memory leaks when under load for extended periods of time?

     
    
    --> Stress Testing - stability, Under what conditions will the system fail?
    The goals of Stress testing is to ensure the software does not crash in conditions of insufficient computational resources (such as memory or disk space). It involves testing beyond normal operational capacity, often to a breaking point, in order to observe the results.

    

==> Security Testing Techniques

    --> Penetration Testing:
    = Simulating an attack from a malicious source
    = Includes network scanning and vulnerability scanning
    = Simulating an attack from someone familiar with the system
    = Simulate an attack by having access to source code, network, passwords
    
    --> SQL Injection
    = Exploits Database Layer Security Vulnerability
    = Unexpected Execution of User Inputs

    --> Cross Site Scripting
    = Injecting Malicious Client Side Script into Web PagesThe malicious code along with the original webpage gets displayed in the web client
    
    --> Parameter Manipulation
    = Cookie Manipulation
    = URL Manipulation
    = HTTP Header Manipulation
    
    --> Denial of Service Testing
    = Flooding a target machine with enough traffic to hinder normal operations
    
    --> Password Cracking
    = Collecting Passwords from the Stored or Transmitted Data
    = Using Brute Force and Dictionary Attacks
    = Identifying Weak Passwords
    
    --> Social Engineering
    = Psychological Manipulation of People
    = Extracting confidential information



    
    -----------------------------------------------------------------





# 6 Testing Techniques

==> Static tests
    Aim to find problems in the design or concept of the prod.
    Code is NOT being executed.
    
    Static Testing Techniques:
    --> Reviews: A human investigator is the primary defect finder
    --> Static Analysis: Testing is done by code review tools



    
==> Dynamic tests
    Aim to find problems in an instance of the product.
    Code execution is mandatory.
    
    Dynamic Testing Techniques: Black Box - White Box - Gray Box
    
    Some of the most used Black Box testing techniques are:

=> Equivalence Partitioning: Classes of values: Separating all test cases in different classes of values.

=> Boundary Value Analysis. Analysis of the limits. 
    Definition: As we know the limits of the availability of the software we test before the limits, between the limits and after the limits of its possibilities


=> Decision Tables: “Reason – Effect” table. Combination of Conditions and Actions regarding the established rules for the software we test. 
    
    
=> State Transition Tables: There’s a limit of conditions and between them the software should have special behaviour.
    Main components and behavior:
    = Conditions that the system can have.
    = Transitions from one state to another
    = What causes this transitions
    = The results of the transitions

    
    
    --> Use-Case Testing
    
    Testing conditions of the software
    
    
==> White-Box Testing Techniques

    = Statement Coverage
    = Branch/Decision Coverage
    = Path Coverage


# 7 Bug Tracking and Version Control Systems

What Do We Report Defects Against?
    ==> The code or the system itself
    ==> Requirements
    ==> Design specifications
    ==> User and operator guides and tests


What is a bug tracking system?
    A bug tracking system or defect tracking system is a software application that keeps track of reported software bugs in software development projects. It may be regarded as a type of issue tracking system.
    
    An incident report usually includes:
    = Date and time of the failure
    = Phase of the project 
    = Test case that produced the incident
    = Name of the tester
    = Test environment
    
    
Severity and priority of the defect
    = Sometimes classified by testers
    = Sometimes a bug triage committee is responsible for that
    = Determines also the risks, costs, opportunities and benefits associated with fixing or not fixing the defect


What is a defect "severity"?
    The degree of impact on the operation of the system
    Possible severity classification could be:
    1 – Blocking: Stops the user from using the feature as it is meant to be used. No reasonable workaround.
    2 – Critical: Data corruption. Easily and repeatedly throws an exception. No reasonable workaround. Feature does not work as expected.
    3 – High: Throws an exception when not following the happy path. Confusing UI. Has a reasonable workaround.
    4 – Medium: Feature works off the happy path with minor issues. Small UI issues. One or more reasonable workarounds.
    5 – Low: Cosmetic issues. Many workarounds. Low visibility to users.


Defect Priority
    Indicates how quickly the particular problem should be corrected. Possible priority classification could be:
    1 – Immediate
    2 – Next Release
    3 – On Occasion
    4 – Open (not planned for now)
    
    
Defect Lifecycle States
    => New: The bug is posted for the first time. The bug is not yet approved
    => Open: The test lead approves that the bug is genuine. Changes the state as “OPEN”.
    => Assign: The bug is assigned to corresponding developer or developer team
    => Test: The bug has been fixed and is released to testing team
    => Rejected: If the developer feels that the bug is not genuine, he rejects the bug
    => Duplicate: The bug is repeated twice or the two bugs mention the same concept of the bug
    => Verified: Once the bug is fixed and the status is changed to “TEST”, the tester tests the bug. If the bug is not present in the software, he approves that the bug is fixed.
    => Reopened: The bug still exists even after the bug is fixed by the developer. The bug traverses the life cycle once again
    => Closed: The bug is fixed, tested and approved


Distributed Version Control: 
    The complete codebase - including its full history - is mirrored on every developer's computer. There is still a master copy of the code base, but it’s kept on a client machine rather than a server. 
    

Centralized Version Control: 
    A centralized version control system works on a client-server model. There is a single, (centralized) master copy of the code base, and pieces of the code that are being worked on are typically locked, (or “checked out”) so that only one developer is allowed to work on that part of the code at any one time. 


# 8 Software Development and Testing Lifecycle

What is a Development Methodology?
    => A development methodology is a set of practices and procedures for organizing the software development process
    => A set of rules that developers have to follow
    => A set of conventions the organization decides to follow
    => A systematical, engineering approach for organizing and managing software projects
    
    
Phases of the SDLC
    => Idea
    => Planning
    => Creating
    => Testing
    => Deploying
    => Maintenance
    The phases of analysis, planning and design are in most cases longer than the initial creation.
    
    
Development Tasks
    1. Requirements specification: Specifying customer requirements. Defining the system’s purpose, characteristics and features
    2. Functional system design: Mapping functions and dialogues of the new system.
    3. Technical system design:
        => Designing the implementation of the system. 
        => Defining interfaces to the system environment
        => Decomposing the system into smaller understandable subsystems 
        => System architecture
    4. Component specification: Defining each subsystem. Task, behavior, inner structure, interfaces.
    5. Programming: Implementing each specified component in a programming language. Modules, units, classes
 
 
 Testing Tasks
    1. Component (unit) test: Verifies each software component does it perform correctly according to its specification.
    2. Integration test: Checks groups of components do they collaborate correctly according to the technical system design.
    3. System test: Verifies the system as a whole does it meet the specified system requirements.
    4. Acceptance test: Does the system meet the customer requirements.
    
    
Validation vs. Verification
    1. Validation: Are we building the right system? Does the product (or a part of it) solve its task? Is this product suitable for its intended use?
    2. Verification: Are we building the system right? Does the product meet its specification? Has it been achieved correctly and completely.
    

Development Methodologies
    Heavyweight and agile methodologies
    => Heavy methodologies rely on formal procedures and documents
    => Agile methodologies rely on small iterations and less formalities
    
Heavyweight:
The Waterfall Model
        The first fundamental model was the Waterfall model
        Only when one development level is completed will be initiated the next one.
        Only between adjacent levels are there feedback loops and revisions of the previous level
        Emphasis is on documentation
        Testing is understood as a "one time" action at the end of the development
        
        The Waterfall Model - Advantages:
        => Simple and easy to use and apply
        => Easy to manage it 
        => Phases rule
        => Very useful for small projects with strong configuration of requirements. 
         
        The Waterfall Model - Disadvantages:
        => Hard to apply clients change request
        => Risk 
        => Useless when an object oriented language is used
        => Not useful for long term projects
         
V Model Development Process
The model presents two branches: 
        => Development tasks: The process of design and implementation.
        => Testing tasks: Verification and integration into bigger subsystems. Both are corresponding activities of equal importance
        
        V Model - Advantages:
        => Simple and easy to use
        => Creating test documentation, test planning and performance testing is on same time as development.
        => Bugs found at the very beginning 
        => Small projects
        
        V Model - Disadvantages:
        => Not flexible
        => If there is change request in the middle of coding, the requirements should be changed.
        
        
Iterative Development Models:
        => Develop a system through repeated cycles (iterative) 
        => Smaller portions at a time/cycle (incremental) 
        => Learn during development of previous parts or versions of the system 
        => Plan-do-check-act cycle
        
        Advantages:
        => Produces business value early in the development life cycle
        => Verification and validation 
        => Can be carried out on each increment
        => Take advantage of what was learnt 
        => Product update at each iteration
        
        Disadvantages:
        => Tempts you to start coding before you have a clear idea of what you want to do
        => Requires more customer involvement than the linear approaches
        => Partitioning the functions and features might be problematic
        => Regression testing 
        => Increasingly important on all iterations after the first one
        
Initialization Step
        => Creating a base version of the system
        => Create a product to which the user can react
        => Sampling of the key aspects of the problem 
        => Solution that is simple enough to understand and implement easily 
        
        
Iteration Step
        => Design and implementation of a task from the project control list
        => Analysis of the current version of the system
        => Analysis of the structure, modularity, usability, reliability, efficiency & achievement of goals
        => Iteration analysis is based upon user feedback, and the program analysis facilities available
        
        
Project Control List
        => Created to guide the iteration process
        => Contains a record of all tasks that need to be performed
        => New features to be implemented
        => Areas of redesign of the existing solution
        => Constantly revised as a result of the analysis phase    
        
        
Types of Iterative Models
    => Agile Development - “Our highest priority is to satisfy the customer through early and continuous delivery of valuable software“
    Individuals and interactions -- over -- Processes and tools
    Working software             -- over -- Comprehensive documentation
    Customer collaboration       -- over -- Contract negotiation
    Responding to change         -- over -- Following a plan
    
    
    --> Satisfy the customer by providing useful software fast
    --> Change requirements are possible long and late in the project
    --> Provide software in short periods
    --> Running software is the main measure of progress
    --> Stable development for constant velocity
    --> Cooperation between the team members constantly
    --> Face-to-face communication
    --> The project is build in highly motivated team 
    --> Continuous attention 
    --> Simplicity – max work for min time
    --> Self-organizing teams
    --> Regular adaptation to changing the circumstances
    
    
Extreme Programming
    A type of agile software development. Intended to improve software quality and responsiveness to changing customer requirements 
    Advocates frequent "releases" in short development cycles (time boxes). 
    Intended to improve productivity 
    Checkpoints where new customer requirements can be adopted.
    Values:
    => Communication
    => Simplicity
    => Feedback
    => Courage
    => Respect
    
    
Kanban
    Kanban is a method of managing activities with an emphasis on delivery just in time without team members being overloaded.
    The name – literally translated from Japanese means “Alert card”
    Requires real-time communication of capacity and full transparency of work
    Project management tool designed to help visualize work
    The work revolves around a kanban boards
    A basic kanban board has a three-step workflow: - To Do, - In Progress, and - Done
    
    => There are no sprints/iterations
    => There are no meetings as planning and retrospectives
    => There are no predefined teams – each member of the team canwork on more than one project
    => Synchronized task progress
    => Visual Signals. Columns. Work In Progress (WIP) Limits. “Set the maximum amount of work that can exist in each status of a workflow”
    Commitment point. Delivery point
    
    
Scrum
    A framework within which people can address complex problems, and productively and creative delivery products of the highest possible value
    Scrum is an iterative and incremental agile software development methodology for managing product development
    An agile process that allows us to focus on delivering the highest business value in the shortest time
    It allows us to rapidly and repeatedly inspect actual working software (every two weeks to one month)
    
    => The business sets the priorities
    => Teams self-organize to determine the best way to deliver the highest priority features
    => Every two weeks to a month anyone can see real working software and decide to release it as is or continue to enhance it for another sprint
    
    Roles:
    => Scrum Master – Links the team to the product owner. Maintains the Scrum processes. Scrum Master facilitates work rather than managing it. He's not the team leader. Acts as a buffer between the team and any distracting influences
    
    => Product Owner – represents the stakeholders. Represents the voice of the customer. He is accountable for ensuring that the Team delivers value to the business. Writes customer-centric items (typically user stories). Prioritizes them, and adds them to the product backlog 
    
    => Team – a group of about 7 people
    The Team is responsible for delivering the product. Typically made up of 5–9 people. Team members have cross-functional skills 
    The team does the actual work. Analyze, design, develop, test, technical communication, document, etc.
    
    => Burndown charts
    Scrum uses a burndown chart during sprints to let team members see progress at a glance. Rather than displaying completed tasks, the burndown chart visualizes what’s left to be done. It should be continuously updated to help team members manage their workflow.
    
    
    Scrum Terminology:
    => Sprint: An iteration in Scrum - usually few weeks.
    => Backlog: All features that have to be developed
    
    Product Backlog:
    A high-level list with broad descriptions of all potential features for the product (backlog items).
    Maintained throughout the entire project. Prioritized by the product owner. Open and editable in terms of years.
    
    Sprint Backlog:
    The list of work the team must address during the next sprint. Features are broken down into tasks between four and sixteen hours of work.
    Tasks on the sprint backlog are never assigned in terms of weeks.
    The sprint burn down chart is a publicly displayed chart. Shows remaining work in the sprint backlog. Updated every day, it gives a simple view of the sprint progress.
    
    Bug Backlog
    A type of backlog which includes bugs only. Can be part of the Product Backlog. Bugs are listed by their priority.
    Includes bugs reported by customers. Bugs are prioritized by Product Owner, supported by QA lead.
    
    Scrum Meetings:
    => Sprint Planning Meeting: At the beginning of the sprint cycle. Establish the Sprint backlog.
    => Daily Scrum stand-up meeting: Team members share progress details. Timeboxed to 15 minutes.
    => Sprint Review Meeting: Review the work completed / not completed.
    => Sprint Retrospective.
    
    
    Kanban vs. Scrum Board
    Scrum:
    => Sprints have start and stop dates 
    => Team roles are clearly defined in scrum (product owner, dev team, scrum master)
    => Scrum board has a set number of tasks and strict deadline to complete them.
    => Release at the end of each sprint, if approved by the product owner

    Kanban:
    => An ongoing process.
    => Has no formal roles. Both teams are self-organized.
    => A kanban board is used throughout the lifecycle of a project.  
    => Continuous delivery or at the team's discretion
    
----------------------------------------------  

--> The Kanban: STRICT LIMITS on the amount of work in progress at any given time.
    --> Continuous improvement:
    The Kanban methodology requires strict limits on the amount of work in progress at any given time. Teams assign a limit to the number of cards in any active-work columns. When the limit is met, no new work can enter the column until a task is completed and moved to the next column. Again, this system helps teams identify bottlenecks, and it encourages individual contributors to rally together to fix them. 
    
--> Scrum: TWO-WEEK SPRINTS
    It is another Agile methodology that uses an incremental approach to work in order to complete projects more quickly. If you're looking at Kanban vs. Scrum, Kanban is primarily concerned with process improvements, while Scrum is concerned with getting more work done faster. 
    --> Sprints
    Scrum uses TWO-WEEK SPRINTS to get work done. These sprints are planned in advance, executed, and then reviewed at the end of the two-week period. During sprint planning, the team creates a sprint backlog. The team completes these backlog tasks during the sprint, managing the work among themselves. Team members also hold a 15-minute Scrum meeting each day of the sprint. 
    
    
Which method should you use?
    => Scrum - If you simply want to produce work faster. 
    => Kanban - If you want to improve your production process. 
    => Waterfall - If your projects demand a linear workflow. 
    The best project management methodology for your team is the one you’ll execute perfectly. 
    
----------------------------------------------    
    
Waterfall works best for projects completed in a linear fashion and does not allow going back to a prior phase. 
Agile focuses on adaptive, simultaneous workflows. Agile methods break projects into smaller, iterative periods. 
Kanban is primarily concerned with process improvements, while 
Scrum is concerned with getting more work done faster.



The phases of Software Testing Life Cycle
    => Requirement 
    => Planning – Estimate 
    => Analysis
    => Design
    => Implementation
    => Execution
    => Conclusion
    => Closure
    
    
Entry criteria – rules that needs to be covered so to start the testing activities.
Exit criteria – rules that defined that the testing process can be considered as completed.

    










    => Burn Down Chart: Simple view of the sprint progress



























    
    
    
    => Rapid Application Development (RAD)
    => Rational Unified Process (RUP)








        





         




    






    


