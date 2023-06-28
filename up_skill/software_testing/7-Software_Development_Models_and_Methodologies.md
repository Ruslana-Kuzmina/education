# Sostware Development Models and Methodologies

## Waterfall model

- Analysis
    - Requirements gathering
    - Requirements Specifications preparation 
- Design
    - Architecture
    - DB Design
    - Prototype and wireframes development
- Development
    - Coding
- Testing
    - Test planning
    - Tests preparation
    - Testing and issues traking
    - Conclusions about quality
- Release and Maintenance
    - Application delivery
    - User acceptance
    - Maintenance
    - Support

Feature:

- First Process Model
- Each phase must be complited fully before the next phase can begin
- Each phase should be complited with ideal quality
- The whole product is delivered at the end of development process

When to use:

- Requirements are well documented, clear and fixed
- Highly regulated area like government/military/medical

Disadvantages:


- Mistakes may be found later and be very expensive
- Estimates for all product development phases may be inaccurate
- Features are usually more complex than planned
- As results, milestones are often shifted
- Huge amount of documentation
- Year(s) to get version of a product

### Agile

Values:

**Individuals and interactions** over processes and tool
**Working sofrware** over comprehensive documentation
**Customer collaboration** over contract negotiation
**Responding to change** over following a plan

#### Scrum

Concept:

Product backlog - Sprint planning - Sprint backlog - Sprint (2-4 weeks) - Shippable product

Scrum elements:

- Roles
    - Product Owner
    - Scrum Master
    - Development Team
- Events
    - Sprint Retrospective
    - Sprint Review
    - Sprint Planning
    - Daily Scrum
- Artifacts
    - Product Backlog
    - Sprint Backlog
    - Product Increment
- Other
    - Release Burndown
    - Impediment
    - Sprint Burndown
    - Backlog Refinement
    - Tasks
    - Product Backlog Item

Scrum Roles:

Producr Owner:

- Clears user stories for the development team
- Sets **priorities** for the stories
- Responsible for initial **planning**
- Communicate with the rest of the company

Scrum Master:

- Responsible for ensuring Scrum is understood and enacted by **Product Owner** and
  **Development Team**
- Resolves Team **impediments**

Development Team:

- Self-organized, small team
- **Cross-functional**, with all of the skills as a team necessary to create a
  product Increment
- No titles and sub-teams

Scrum Events

- Sprint Grooming (Backlog Refinement) - Usually perfomed before the sprint

Team:

- Clarify requirements to use stories
- Ask questions to Product Owner
- Define how story can be developed and tested

Sprint Planning - usually performed on the 1 day of a sprint

Team:

- Reviews high priority **stories**
- Select stories for **sprint**
- Breaks stories into tasks and estimates tasks execution

Daily Sprint/Stand-up

- Scrum master tracks and resolves challenges
- 10-15 minutes
- Face 2 face communication is appreciated
- Each team member describes:
    - what is done
    - what is planned
    - challenges if any

Sprint Review / Demo - usually performed at the end of a sprint when scope is ready

- Developer/Tester/BA responsible for the feature demonstrates the work that was Done
- Receives feedback from customer

Sprint Retrospective

- What was done **well**
- What could be done **better**
- Assign **responsible** person
- Set **timelines** for changes 

TEST:

- What does every team member speak about during stand-up meeting?

    - [ ] How did a sprint pass?
    - [x] What did he do yesterday?
    - [x] What is he going to do?
    - [ ] How much time does each story take in a sprint?
    - [x] What difficulties does he have?

- What does a team discuss during a sprint retrospective?

    - [x] What was good about a sprint?
    - [x] What was bad about a sprint?
    - [ ] How many tasks to take for the next sprint?
    - [ ] Which stories will be passed to the next sprint?

- What exactly is a perfect burndown?

     - [ ] Point
     - [x] Right line
     - [ ] Parabola
     - [ ] Hyperbola

- How often is stand-up meeting?

     - [ ] Twice a day: in the beginning of the day and at the end
     - [x] Once a day
     - [ ] Once a week, usually on Monday or Friday
     - [ ] In the beginning of every sprint
     - [ ] At the end of every sprint

Choose the correct statements

     - [x] Product Owner makes the details of the stories clear to the development team
     - [ ] Scrum Master decides which stories are going to be carried into the sprint
     - [x] Scrum-team usually comprises of about 10 people, more often 4-5 people
     - [x] Backlog refinment (grooming) is carried out before the sprint start
     - [ ] Stand-up meeting usually takes around an hour
     - [x] Sprint Review (Demo) is a meeting during which a team demonstartes the
           results of its work in a particular sprint

##### Kanban

Why Kanban:

- More flexibility with scope - don't need to fix backlogeven for 2 weeks
- Good visualization tasks progress - task board, colors, labels, filters are
  wildly used
- Easy to start - don't need to set up process according to the framework, move
  step by step as you wont

Kanban suits for the teams that:

- Support product
- Have a lot of changes in backlog during the sprint
- Do not have clear described user stories in sprint backlog
- Have dependences from other team (separate back-end and front-end dev-teams)
- Support other teams like automation/design/DevOps

###### Extreme Programming

- The Planning Game
- Short Release
- Metaphor
- Simple Design
- Testing: unit tests, automated tests
- Refactoring
- Pair Programming
- Collective Ownership
- Continuous Integration
- 40 hours week
- On-site Cistomer
- Coding Standarts

####### Test-Driven Development

Red - Green - Refactor

- Clean readable well-designed code
- Safe refactoring
- Decrease technical debt on the project
- Stable team velocity
- Many teams report significant reductions in defect rates

TDD approach requires significant changes from developers and takes time

TEST:

- Select the most right description of the actions within TDD approach.

    - [ ] Develop a feature then implement testing
    - [ ] Develop a feature, implement testing, then launch refactoring
    - [x] Implement tests, develop a feature, then launch refactoring
    - [ ] Launch refactoring, implement tests, develop a feature

- How many tests do we need to consider a feature as ready and decently tested?

    - [ ]One test is enough
    - [ ] Five tests are enough
    - [ ] Ten tests are enough
    - [x] Depends on the feature

Notes: Yes. There are simple features and there are complex ones. There is critical functionality, that can require more thorough testing. TDD practice does not rely
on some precise numbers, this is left to developers.

- Why are the tests written for functionality development more efficient?

    - [ ] Developer is not yet tired with coding. The efficiency of a developer
          decreases in time and by the end of working day it falls to zero or even
          below zero.
    - [x] Developer does not yet know what the implementation will be, and that
          means that he does not have any prejudices about the algorithm decision
          implementation.
    - [ ] Developer always knows what the implementation will be, that's why he
          implements tests based on the future branches, including those that
          contain defects.

######## Behaviour-Driven Development

Business owner tell the business analyst what he wants
                          |
                          V
         Business analyst write requirements
              |                        |
              V                        V
Developer translate          Tester translate          Technical writer translate
requirements into            requirements into         sofrware into technical
software                     test cases                documentation
          |                           |                      |
          V                           V                      V
                                    Product

This is ordinary situation.

BDD

Business owner discuss with analyst what business wants
                          |
                          V
Business together with developer and tester elaborates "scenarios"
                          |
                          V
                      Scenarios
            |                     |                                   |
            V                     V                                   V
Automated tests provide      Developer use scenarios as       Tester use scenarios
feedback on progress         a guide, test and acceptance     as a base for tests
                             criteria
                                         |                              |
                                         V                              V
                                                 Product

Summary:

- Agile is philosophy with values and principals, but not strict instructions
  how to build process
- Kanban, Scrum are frameworks that have instructions how to set up process
- XP practices, TDD abd BDD can be easy integrated into Scrum or Kanban process
















