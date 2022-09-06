# The Software Development Life Cycle (SDLC)

- **Requirement definition**
  During the Requirement Definition stage, a Business Analyst collects the input
   from stakeholders trying to understand their 'true' needs and what goals they
   are trying to pursue. In addition, the objectives of the initiative are
   defined, and a Business Analyst ensures that everyone involved has a shared
   understanding of those objectives.

- **Analysis**
  During the Analysis stage, a Business Analyst elaborates on the high-level
  requirements received in the previous phase. Further to that, the team
  determines the cost and resources required for implementing the identified
  requirements. The risks associated with the initiative are analyzed to work
  out the mitigation plan if needed.

- **Design**
  During the Design stage, solution architecture is designed and described in
  a document. Moreover, the phase implies creating prototypes of the envisioned
  solution. Generally, prototyping proved itself to be useful for getting early
  feedback and eliminating risks associated with future development.

- **Coding**
  During the Analysis stage, a Business Analyst elaborates on the high-level
  requirements received in the previous phase. Further to that, the team
  determines the cost and resources required for implementing the identified
  requirements. The risks associated with the initiative are analyzed to work
   out the mitigation plan if needed.

- **Assurance**
  During the Quality Assurance stage, the product is tested to confirm its
  quality and value for end users. Any issues found during the testing process
  should be fixed until the software meets the expected quality guidelines.

- **Deployment**
  During the Deployment stage, the software is deployed to the production
  environment so that end users can start using it.

- **Maintenance**
  During the Maintenance stage, the existing product might be enhanced with new
  features, or any errors detected by real customers will be fixed as a part of
  this phase. Active development is not expected during the Maintenance stage.
  however, the product should constantly evolve to support fast-changing business
  needs.

## SDLC models

### Traditional

Are plan-driven and are focused on minimizing the upfront uncertainty and
maximizing control. Software development governed by a traditional methodology
has a sequential flow where the next phase does not start until the previous one
finishes.

#### Waterfall model

Phases:

- Requirements
- Analysis
- Design
- Coding/Implementation
- Testing
- Operation/Deployment
- Maintenance

The Waterfall model is usually associated with tons of requirements documents,
predefined templates, and a rigid approval process. The use of Waterfall in
modern IT is rare.

The model is applicable to small projects if:

- the requirements are known, understood, and well documented
- there are no conflicting requirements
- there is no problem with the availability of Developers with the required
  qualification level
- the product to be developed deals with the high-risk area (medical care,
  military industry, aircraft industry, etc.)

#### Advantages

- Is easy to use while managing a project
- Due to its rigidity, development is fast, cost and timeframe are predetermined

#### Disadvantages

- The product is not accessible for stakeholders until the very end of the project.
- The model is not flexible to accommodate changes that might be needed during
  software development.
- It is difficult to elicit all the requirements upfront and discover the ways
  of their possible implementation; most projects start with some level of
  uncertainty. Details are refined as the work on the project continues.
- Developers are required to write a lot of technical documentation which delays
  work.
- Problems in the system can only be discovered late in the process (during the
  Testing phase) due to a strict sequence of phases, and there might be little
  time left for fixing the found issues.

#### Examples

Rational Unified Process (RUP) and V-Model

### Agile

Is change-driven and focused on the rapid delivery of the business value

#### Advantages Agile

- Is change-driven and focused on the rapid delivery of the business value
- Agile accepts a greater level of uncertainty and risk related to the overall
  solution delivery
- Iterative development
- Early feedback
- Adaptability to changes
- А Business Analyst work during all projects
- Agile does not require a Business Analyst to write formal detailed documentation.
  Instead, is expected to write user stories and acceptance criteria with enough
  details, leaving enough room for conversations between a team and a Product Owner.

## Agile Mindset, Values, and Principles

Agile is a **Mindset** that is described by **Values**, defined by 12 **Principles**,
and manifested through an **Unlimited Number of Practices** (SCRUM, XP and CUSTOM).

### Agile Mindset consists of 9 characteristics

- **Quality Consciousness** - is keen on improving the quality of the product.
  This is done through refactoring, code reviews, and different types of testing.
  It is extremely important for teams to remember that the customer pays not only
  for the developed functionality but also for the provided quality.
- **Continuous learning** - hould always learn and self-develop. This helps to
  be on track with new technologies and succeed in new challenges.
- **Failure acceptance**- should be ready to accept failures and learn from
  that experience.
- **Positive attitude** - should have a positive attitude towards work. Any
  challenges that they may face along the way should be transformed into opportunities.
- **Collective ownership** - Agile team members are collectively responsible for
  the product they are producing and for the success of this product. That is why,
  blaming, finger-pointing, unhealthy competition are not acceptable in the Agile
  environment.
- **Team work** - sets the primary focus on team success versus individual success.
  Team members should help and train each other to work effectively and fulfill their
- **Common Goal** - An Agile team should be focused on short-term and long-term
  goals that derive from the product vision and align with the organization's strategy.
- **Customer focus** - can be characterized as a customer-centric approach;
  that is why it is associated with flexibility when it comes to changes and
  early customer feedback.
- **Empowered team** - should be given enough authority to make decisions in
  their area of responsibility.

### Agile Manifesto Values described by 4 core values

- **Individuals and Interactions over Processes and Tools** - People build the
  software systems, and to succeed in that, they need to work together effectively.
  The Agile Manifesto encourages communication between teams instead of relying on
  procedures to manage the way forward.
- **Working Software over Comprehensive Documentation** - Working software will
  bring more business value than documents and slide decks that describe a future
  system. Agile doesn’t defy documentation completely; it offers to a team to start
  creating software rather than spend months creating extensive documentation.
  Requirements should be documented well enough to start the development.
- **Customer Collaboration over Contract Negotiation** - Only customers can tell
  you what they want. Of course, they probably do not have the skills to exactly
  specify the system. Of course, they are likely to change their minds somewhere
  in the midway. Working together with customers is hard but the benefit it usually
  brings can be hardly overestimated. In Agile, the development should be human –
  centered so only communication with customers can uncover the real need of building
  the software.
- **Responding to Change over Following a Plan** - The priorities in the feature
  development might change overtime, even the whole concept of the product can change.
  This might be triggered by market trends, competitors’ achievements and changes
  in the organization priorities. Any change is the reality of software development.
  There is nothing wrong with having a project plan; in fact, you would be worried
  about any project that does not have one. However, there must be room for changes;
  otherwise, the initial plan quickly becomes irrelevant.

## Scrum Overview

Scrum is an iterative and incremental software development framework that is
based on Agile values and principles. Typically, the Scrum framework presupposes
that the development team delivers working product pieces (called **product
increments**) in order of priority and value set by the customer.

In traditional models, there are separate phases, and the results can be seen
when all phases are finished. People from different functional areas (Testers,
Developers) are isolated within a certain phase which makes communication in
a team really challenging.

Scrum is divided into time-boxed iterations, called **sprints**. During a sprint,
a team implements all phases for a specific set of requirements. The duration of
a sprint can range from one to four weeks.

### Scrum can be characterized by the following statements

- Iterative development: each iteration usually takes several weeks and provides
  a full working version of the software
- There is continuous communication and collaboration between the teams involved
  in the development process, including a client or stakeholders
- Early customer feedback is a part of this framework

### Scrum discribed

#### Roles

- **Product Owner = Bisuness**
  A Product Owner (PO) is a stakeholder representative and the voice of a customer.
  A PO is accountable for the business value delivered by a team. A Product Owner
  maintains a product backlog by writing features (user stories) and prioritizing
  them. A Product Owner is the one who owns the vision of the successful product
  and its functionality. A PO also accepts and rejects the final results of the
  work. In some projects, some responsibilities of Product Owners (requirements
  clarification, documenting user stories, etc.) can be performed by a Business
  Analyst. In this case, a Business Analyst works as a"proxy" Product Owner.
- **Scrum Master = Process**
  A Scrum Master helps Scrum team members achieve their highest level of
  performance. A Scrum Master differs from a traditional Project Manager in
  many ways, including the fact that the former does not assign tasks to
  individuals or provide day-to-day directions to a team. A good Scrum Master
  shelters a team from outside distractions allowing Scrum team members during
  the Agile sprint to focus on the goal they have selected.
  - **Team = Delivery**
  A development team is responsible for the achievement of sprint goals and the
  delivery of product increments at the end of each sprint. According to the
  Scrum framework, a development team should consist of 5–9 specialists with
  cross-functional skills. They do the actual work, such as analysis, design,
  development, testing, etc. A development team is self-organized, and ideally,
  there are no titles, which enables all team members to help each other do the
  same work. Each person contributes as much as possible to make sure that the
  team completes the work of each sprint. A team has a shared commitment to
  achieve the sprint goals and it is expected that individuals will work beyond
  their preferred disciplines whenever they can in order to deliver a valuable
  product. It means that Developers, Business Analysts, Testers have their primary
  esponsibility; however, at the same time, they can help each other to complete
  tasks. For example, Developers and Business Analysts can help Testers to test
  new features and deliver product increments in time.

#### Events

- **Sprint Planning** - meeting where a team decides on how much work they will
  be capable of doing during the sprint
- **Daily Scrum** - meeting where team members share statuses on the work that is
  completed and is planned to be completed
- **Sprint Review** - meeting to show a Product Owner the work they have done
  during the sprint.
- **Sprint Retrospective** - meeting is used by team members to reflect on
  their processes and find room for improvement.
- **Backlog Grooming** - meeting, during which a PO and a team add necessary
  details to product backlog items, add new features, split large features, if
    necessary, prioritize and estimate the features.

#### Artifacts

- **Product Backlog**
- **Sprint Backlog** - is a list of product backlog items that a Scrum team
  identified as the ones to be completed during a Scrum sprint. A team takes
  to a sprint backlog the items from the top of a product backlog as they have
  the highest priority. Usually, product backlog items are represented as user
  stories with the sub-tasks required to complete each user story.
- **Product Increment** - The product increment is a summarizing notion that
  includes all product backlog items completed during a sprint and integrated
  with the work from previous sprints. A product backlog item can be added to
  the increment only if it is done. A product increment must be in a useable
  condition; it means that it can be released to production.

#### Features (Auxilary)

- **Scrum board**
- **Burndown chart**
