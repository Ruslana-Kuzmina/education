# Algorithm design and Modern Software Development Process Models

## Modern Software Development Process Models

Software Development Life Cycle:

- Requirement definition - Mathematical or informational formulation of a problem

- Analysis - The choice of numerical or other methods for solving the problem

- Design - The construction of an algorithm for solving the problem

- Coding - The choice of a programming language in order to write the constructed
  algorithm according to its rules, i.e. writing the text of the program

- Assurance - Debugging the program as the process of detecting, localizing, and
  eliminating possible errors

- Deployment - Program execution, i.e. obtaining the required result

- Maintenance - Adding new functions to the program, fixing errors detected by users

Today, we can divide the SDLC models into two large groups:

- "traditional" SDLC (waterfall model)
- Agile

### Waterfall Model

The Waterfall Model (or cascade) is one of the old traditional software development
models which implies a sequential flow of stages, each of which must be fully
completed before the next one starts.

It consist of:

- requirements
- analysis
- design
- coding / implementation
- testing
- operation / deployment
- maintenance

The application of this model in a modern IT enterprise is still rare. It is mostly
used in relatively small projects when:

- the requirements are known, understood, and documented
- there are no conflicting requirements
- there is no problem with the availability of programmers of the right qualifications

In addition, this model can be applied when we are talking about high-risk areas.

A typical example of a project where the Waterfall Model is applicable is the
development of military and aircraft programs or the implementation of any change
to a power plant management system. This is because of the strict security and
safety standards, and the requirements that have to be followed under such programs.

#### Advantages Waterfall Model

- The model is easy-to-use for managing a project.
- Due to its rigidity, development is fast, its cost and timeframe are predetermined.

#### Disadvantages Waterfall Model

- The model is not flexible.
- In reality, it is difficult to know the requirements and the ways to implement
  them in advance; most projects start with some uncertainty. Details are being
  refined in the process of working on the project.
- Developers are required to write a lot of technical documentation which delays
  work.
- Problems in the system can only be discovered late in the process (during testing)
  due to the strict sequence of actions and there is little time left for fixing.
  This can lead to potentially catastrophic consequences for the schedule and cost
  of a project.

### V-Model

The V-Model is based on the idea of validation and verification. It inherited
the structure of the Waterfall Model, but in addition, a detailed check and testing
of the product was organized at the first stages of development. Already at the
time when developers write the code, testers write unit tests, that is, they start
testing in parallel with development.

This approach is mostly recommended for small and medium projects when:

- uninterrupted product operation is crucial
- the requirements are clearly defined and fixed, and strict product testing is
  required
- there is no problem with the availability of engineers with the necessary qualifications,
  especially testers

As an example of the situation where V-Model is applicable, one can consider the
following projects: application programs in clinics for monitoring patients, integrated
software for managing traffic lights, and so on.

#### Advantages V-models

- The model is quite easy to use
- Test design and testing activities themselves are performed at the early stages;
  thus, errors and defects can be identified at the early stages which saves time
  and money.

#### Disadvantages V-models

- The model is quite rigid and not flexible
- No prototypes can be created at early stages; therefore, there is a high risk of
  not meeting customer’s expectations
- If a mistake was made during the development of the architecture, then it will
  be expensive to return and fix it, as in the Waterfall Model

### Incremental Model

The development process based on the Incremental Model combines the sequential
functions of the Waterfall Model and consists of several development cycles (the
assembly of modules). The complete system requirements are also divided into
different iterations. New software modules are added at each iteration without
any changes or minor changes to previously added modules. The process continues
until a complete system is created. The development process can go either
sequentially or in parallel.

Incremental Models are used in the following situations:

- when the basic requirements for the system are clear and understandable; at the
  same time, some details can be improved over time
- when an early market launch is required
- if a new technology is used to develop a project
- if there are not enough resources (primarily, human resources of the required
  skills) available
- if there are several risky features or goals

As an example of such development processes, consider the process of creating
social networks when at first only core features were available to users. You can
also consider the steps involved in building a robot. In the Incremental Model,
each piece is a coherent element. First, we released a simple robot. Let's imagine
that it became sought-after and producers decided to make it faster and increase
the range and, therefore, added wheels and an antenna. In parallel with this, the
development of the touch panel was carried out, which we added at the last stage
and received the product that does not need further refinement and that everyone
is happy with it.

#### Advantages Incremental Model

- The working versions of the software are ready at the early stages of functionality
  development process; so far, users are allowed to use some of the core functionality
  and provide their feedback.
- If there is a parallel development, it also increases the speed of execution of
  the whole project.
- The flexibility of the process is higher than in case with Waterfall or V-Model.
- It is easier to test and debug small pieces of the product during each run.
- There is a lower risk of the overall failure because risky pieces can be found
  earlier, and users' feedback is collected starting from the very first versions.

#### Disadvantages Incremental Model

- The model requires good planning and design.
- If there are many repetitive cycles of sequential development, it can make the
  project time-consuming and expensive.
- The final product should be clearly specified at the very beginning of the process
  in order to break its development down into incremental stages.
- Total development costs are usually higher than that of Waterfall.

### Iterative Model

With the Iterative Model, the creation begins with the definition and implementation
of a part of the functionality which becomes the basis for defining further requirements.
This process is repeated. The version may not be ideal, the main thing is that it
works. Since each iteration is built on the previous one, the design often remains
the same.

The Iterative Model is best used when:

- the requirements for the final system are clear and understandable in advance
- the project is large or very large
- the main challenge needs to be defined but the details can evolve over time
- the development team uses and learns new technology while working on the project
- there aren't any high-risk features and goals that may change in the future

Typically, iterative development is used in conjunction with incremental development,
in which a longer software development cycle is broken down into smaller segments
that build on top of each other.

An example of iterative development is voice recognition. The first research and
preparation of the scientific apparatus began long ago, in the beginning - in
thoughts, then - on paper. With each new iteration, the recognition quality has
improved. However, perfect recognition has not yet been achieved; therefore, the
problem has not been fully solved yet. Or consider iterative "development" of a
robot. As you can see, in the first iteration, there is only its layout, as we
imagine it; in the second iteration, the details from different materials appear,
and the third iteration completes the process and allows the robot to be used in
a certain environment.

#### Advantages Iterative Model

- The working versions of the software are ready at the early stages of the
  functionality development process; so far, users are allowed to use some of the
  core functionality and provide their feedback.
- Changing requirements and project scope is more flexible and less expensive than
  in Waterfall or V-Model.
- Overall costs of the development process are usually lower than under other models.
- There is a lower risk of the overall failure because risky pieces can be found
  earlier, and users’ feedback is collected starting from the very first versions.

#### Disadvantages Iterative Model

- The model requires good planning and design.
- It might be quite time-consuming as each development stage is quite rigid and
  there should not be any time overlap between the stages.
- The overall system architecture should meet all the requirements that arise
  during the software development process and sometimes they cannot be clearly
  predetermined.

### RAD Model

RAD (Rapid Application Development) Model is an incremental development model.
In RAD model, highly qualified teams in parallel, like several mini-projects,
are developing components and functions. The time frame for one cycle is strictly
limited. The generated modules are then assembled into one working prototype in a
short time period. RAD model allows to quickly show a client something working,
get feedback, and introduce changes.

Rapid application development model includes the following steps:

- **Business modeling**: we form a list of information flows between different
  departments
- **Data modeling**: based on the previously collected information, we determine
  the objects and other entities necessary for the exchange of information
- **Process modeling**: we establish links between simulated data to achieve
  development goals
- **Building the application**: it uses auto assembly tools to convert models of
  computer-aided design (CAD) system to code
- **Testing**: new components and interfaces are tested

RAD model should only be used when all of the following conditions are held:

- The system to be developed can be reasonably divided into modules.
- There are highly-qualified and highly-specialized architects available for a project.
- The budget of a project is sufficient to pay for these specialists along with
  the cost of ready-made automated assembly tools.
- It can be chosen with comprehensive knowledge of the target business and the
  need for urgent production of a system within 2-3 months

RAD model is not suitable for projects with a high probability of risks or in
the case of developing the systems that have a frequent change of the components'
interfaces.

A typical example of the use of RAD model can be the development of any product
that requires initial requirements collection, development and testing, followed
by deployment and maintenance. Due to the fact that changing requirements can force
a company to start almost every project from scratch and create new template code
before submitting prototypes, the company’s sales cycles can last for months and
it can take over a year for projects to be developed before they go into production.
In this case, it is best to move to application platforms that facilitate rapid
application development by integrating internal and external programming and deployment
into a single visual interface. To gain an advantage over their competitors, Keypoint
Intelligence turned to OutSystems.

#### Advantages RAD

- The development process takes less time.
- System components can be reused during the development process.
- Users’ feedback can be collected at the early stages of the development process.
- There is a lower risk of integration failure because the integration of modules
  starts from the very beginning.

#### Disadvantages RAD

- There are a lot of limitations on the use of this module (discussed above).
- The cost of modeling and automatic code generating is high.
- The result highly depends on the individual performance of team members while
  identifying business requirements.

### Spiral Model

The Spiral Model is similar to the Incremental Model but with a focus on risk
assessment: the next stage builds on the previous one, and at the end of each round,
the team or the customer decides whether to continue the project. This model looks
like a spiral, and with each new turn, the process becomes more complicated. Each
cycle usually includes four stages:

- The determination of requirements and constraints
- Risk analysis and assessment of alternatives
- Project implementation
- Evaluation of the result and, if the quality is satisfactory, the transition to
  a new stage

Work on a project continues until the iterative process is completed in the model.

The Spiral Model is suitable for medium- and high-risk large projects when:

- the costs of a project are quite high and risk evaluation is necessary
- long-term project commitment cannot be taken (e.g. due to a high risk of potential
  changes of external factors)
- users are not sure about their needs and the risk of the change of requirements
  is high
- project requirements are too complex
- we are going to set up a new product line or enter a new market, and the changes
  due to additional research and exploration are highly expected

An example of a project where the Spiral Model is applicable is developing a document
management system for a bank or a smart home system.

#### Advantages Spiral Model

- The model pays great attention to the study of risks.
- There is a strong approval and documentation control.
- There are working versions (with limited functionality) ready for use at the early
  stages of the development cycle while additional functionality can be added at
  later cycles.

#### Disadvantages Spiral Model

- The participation of a large number of experts with experience in risk assessment
  is required.
- An excessive number of iterations might lead to increased development costs and
  delayed application submission.

### Agile Model

Today, more and more organizations are adopting one or another Agile approach in
their IT projects. The Agile Model is an agility-based software development methodology
that was first introduced in 1990. Agile is based on:

- **iterative development**: each iteration usually takes several weeks and
  provides a full working version of the software
- continuous **communication and collaboration** between the teams involved in the
  development process, including a client or stakeholders
- early customer **feedback**

The Agile Model is used:

- in almost any start-up initiative where quick feedback from users is needed
- in medium-sized projects where it’s not difficult to translate business
  requirements into the detailed requirements for a software product
- in large projects that can be easily divided into small functional parts and to
  which an iterative model can be applied

Some Examples of the Agile Model:

- Extreme Development
- Feature-Driven Development
- Test-Driven Development

#### Advantages Agile

- It pays little attention to detailed documentation (plan) of software which
  contributes to its rapid development.
- It places emphasis on software testing.
- Frequent releases are typical: at the end of each iteration, the development
  progress is checked and the importance of tasks for the next iteration is assessed
  in order to increase the return on investment (ROI):
  - It allows to continuously improve the software with simple fixes and changes.
  - It enables quick updates and new functions which makes a software product more
    attractive.

#### Disadvantages Agile

- It pays little attention to the detailed documentation (plan) of the software
  and complicates its maintenance since it takes a lot of time to find the problem
  when there is no detailed description or because the documentation could get lengthy.
- Lack of detailed planning makes it difficult to accurately estimate the required
  budget, development time, and the size of the team required for a project. Quite
  often the costs are higher compared to Waterfall or the Iterative Model.

### XP (Extreme Programming) Model

Extreme Programming Model is an informal and progressive approach to software
development based on the method of agile software development, where each developer
is usually a professional in their field. The core ideas of the model are represented
by a set of values, principles, and practices for the fastest possible development
of high-quality software that provides maximum value for a client during the
development process. The main thing in extreme programming is not to lose control
of what is happening.

One example of project execution using XP is the Ford Motor Cost Analysis System.
The duration of the project was 6 years and the team of 17 people worked on it,
including 12 programmers. Ford Motor's Financial Systems Division have developed
the Vehicle Costing and Profit System (VCAPS), which reports production income,
expenses, net income, and profit. The inputs to the system include engineering
product specifications, fixed costs and expenses, and variable costs such as
working hours. Work on the VCAPS project began in 1993. During development, we used
VisualWorks and GemStone Smalltalk. VCAPS is currently supported by a small team
of specialists and will soon be replaced by a more modern application.

#### Advantages XP

- It is widely used in the development of small software projects with high risk.
- Product development is carried out in short iterations.
- It has the advantage of adapting to rapid changes in user requirements in the
  IT field.
- It allows developers to focus on coding and avoid unnecessary work related to
  document management.
- The customer receives exactly the product that they need even if at the beginning
  of development, they do not have an exact final picture of this product.
- A team easily maintains the code as it is written according to a single standard
  and is constantly refactored.

#### Disadvantages XP

- In software development, the first simple solution that was accepted and launched
  might turn quite risky for a project.
- The success of a project depends on customer involvement which is not easy to
  enhance.
- It is difficult to predict the time spent on a project because in the beginning,
  no one knows the entire list of requirements.
- XP success is highly dependent on the level of programmers, the methodology is
  implemented effectively only by senior specialists.
- Regular meetings with programmers are expensive for customers.

Today, the most common Agile subtypes are Scrum and Kanban which are called
frameworks. A **framework** is a more mature methodology with strict rules.

### Scrum

Since this model has evolved from Agile, it consists of the same stages as the Agile
Model. According to this model, a Scrum Master is often a part of a team and he/she
ensures the continuous work of the whole team by creating the necessary conditions
for it: keeping morale high, organizing procedures, facilitating meetings. There
is also a Product Owner on a project – a person who leads the development, monitors
the product, and like a business analyst, acts as the main link between the client's
mission and the result of a team. Iterations ("sprints") usually last no longer than
1 month and are preceded by careful planning and evaluation of the previous sprint.
Once the sprint actions are defined, no changes are allowed. Such a system is suitable
for projects with a small team of up to ten people.

### Kanban

Kanban ("card") is distinguished by its visualization of the life cycle and the
lack of vivid iterations. A team organizes work using a virtual whiteboard which
is divided into project stages. Each stage must go through all the columns - To do,
In progress, Code review, In testing, Done (columns can be changed individually).
Each team member sees which tasks are in progress, which ones are stuck at one of
the stages, and which ones have already reached the necessary column and require
attention. The goal of each team member is to reduce the number of tasks in the
first column, since you can take urgent tasks into development right away without
waiting for the start of the next sprint. This approach makes it easy to understand
where the problem has appeared and provides a chance to see how the entire project
is organized.

## The Concept of an Algorithm, Types of Algorithms

Algorithmization is the presentation of a task in the form of sequential steps
so that the results of previous actions are used when performing the next actions.

The description of the sequence of actions (steps) that must be performed to obtain
the desired result is called an **algorithm**. In other words, an algorithm is a
strict and clear set of rules that determines the sequence of actions that lead
to the achievement of the set goal to obtain the result for a given input.

In order to create a good algorithm, you need to carefully analyze the condition
of a problem. Analysis is the study of objects or phenomena by studying their
constituent elements.

The analysis of a problem allows you to:

- establish what the input and output of the future algorithm are, while the input
  data should be explicitly described (the input data is determined by the imposition
  of constraints)
- highlight key decisions (dependencies) between input and output data
- highlight the modules necessary to solve the problem and determine the methods
  for its solution

The definition of the relationship between input and output data is often determined
by the mathematical formulation of the problem being solved. The mathematical
formulation of the problem answers four questions:

What is given? - All source data are listed.
What is needed? – It lists all outputs with their names and mathematical notation.
What results will be considered correct? – It establishes a mathematical statement
system linking inputs and outputs with an explanation of each record.
What data will be considered valid? – It establishes a system of mathematical
statements that impose restrictions on the area of admissible input data.

Properties of an algorithm:

- **Efficiency** (finiteness): an algorithm solves a problem in a finite number
  of steps and the prescribed solution is guaranteed to give a correct answer
- **Discreteness**: new data values are calculated according to certain rules
  from other variables with already known values
- **Certainty** (determinism): each rule from the set is unambiguous, and the data
  themselves are unambiguously related to each other.
- **Sequence of execution**: the sequence of actions of an algorithm is strictly
   and precisely defined.
- **Massiveness**: an algorithm is developed so that it can be applied to a whole
  class of problems, for example, an algorithm for calculating certain integrals
  according to given accuracy.

### Ways to Describe Algorithms

There are several ways to describe algorithms. The most common ways are verbal,
or pseudocode, and graphical description of an algorithm, or a flowchart.

#### Verbal Description of an Algorithm

Pseudocode specifies the steps of an algorithm using essentially natural language
and through the use of the following control constructs:

- The step (stage) of processing (calculating) data values - "=".
- The step of checking a logical condition: if (condition) is true, then perform
  action 1; otherwise - action 2.
- The transition (transfer of control) to a certain step (stage) N.

#### Graphic Representation of an Algorithm

The graphic representation of an algorithm (or a program flowchart) is its representation
in the form of a diagram consisting of a sequence of blocks (geometric shapes),
each of which displays the content of the next step of the algorithm. The action
performed in this block is briefly recorded inside the figures.

Flowcharting guidelines:

- A flowchart should flow from top to bottom.
- If a chart becomes complex, utilize connecting blocks.
- Avoid intersecting flow lines.
- Use meaningful description in the symbol. Single keywords or short phrases will
  make a flowchart clearer and more concise.

You can create flowcharts of programs manually, or you can use numerous special
creation tools.

When we implement loops using flowcharts, the arrow after the statements in the
part "Yes" can go into the conditional block, or possibly into the branch leading
to it.

## Drawing Linear, Branching, and Looping Algorithms

Any program can be divided into blocks implemented in the form of algorithms
(processes), which can be divided into three types, and can draw a flowchart
for each of them:

- **Sequence**: a series of steps, and each step will be executed one after another.
- **Branching**: the direction of execution determines the condition represented
  by the "if-else" and "switch" statements. If a condition is true, there will
  be one output; if the condition is false, there will be a different output. This
  algorithm type is also known as "selection type".
- **Loop**: separate sections of calculations might be repeatedly executed under
  a certain condition. It is represented by "while" and "for" problems. Make sure
  the process will end after several loops under the condition. Any loop process
  includes a branching section and can be simple or complex (nested). To solve the
  question of how many times a loop needs to be executed, a variable analysis is
  used, which is called a loop parameter.

Arrays are often used in solving mathematical problems. An array is a set of elements
of the same type, ordered by indices that determine its position in the array row.
In the simplest case, an array has a certain length (size), stores data values of
the same type, and integers act as indices (numbers of places of values). The numbering
starts at zero and the last element has an index (size-1). Usually, the elements
of an array are represented by input and output in a loop, where the index is a
counter. We will explore arrays in more detail later.






