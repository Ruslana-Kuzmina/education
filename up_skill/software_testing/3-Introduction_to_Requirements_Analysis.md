# Introduction to Requirements Analysis

- What is Requirement and Why Requirements are Important
- Ways of Requirements Gathering
- Requirements Levels and Types
- Good Requirements Properties
- Requirements Testing Techniques

## What is Requirement and Why Requirements are Important

**Requirement** – a condition or capability needed by a user to solve a problem
or achieve an objective that must be met or possessed by a system or system component
to satisfy a contract, standard, specification, or other formally imposed document.

## Ways of Requirements Gathering

- Interview 
- Meetings and Brainstorming 
- Questioning
- Observation
- Prototyping 
- Modeling
- Documentation Analysis
- Work with Focus Groups
- Self-(re)writing

**Interview** – the most common way of identifying requirements. Usually, two main
roles involved: interviewer (project specialist, BA) and interviewee (customer
representative or expert, user, etc.). 

*Advantages*: Fast, easy, no special sophisticated techniques required. Everybody
understands the concept, so everybody can participate. Variations possible: in-person,
via (video) call, e-mail, messenger, etc. 
*Disadvantages*: Often some visual aids are required. It takes time to rework the
results as a useable set of data. Interviewer bears the most responsibility for
the results.

**Meetings and Brainstorming** – unlike with Interview, several people are playing
active role here to share information, discuss issues and be on the same page immediately.

*Advantages*: Several key people share information and receive feedback at once. Meetings
are faster than e-mail/messenger communication. “Collective thinking” may create new
good ideas. 
*Disadvantages*: Meetings take time. A lot of time. No, really, A LOT OF TIME. Sometimes
it’s difficult to gather all necessary people together. With intense rhythm meetings
become boring and inefficient.

**Questioning (and questionnaires)** – is a fast and easy way of gathering
and aggregation of information from thousands of respondents. When organized properly, questioning brings a lot of useful results. 

*Advantages*: Great audience coverage – thousands and millions of respondents. Nice
data processing and visualizing capabilities. Possibility to easily compare several
results (over time). 
*Disadvantages*: If held improperly (bad questions, wrong target audience, demotivated respondents and so on), the questioning can give us no data, mess data or (in worst
case) wrong data that looks like a good one.

**Observation** – is a method that shows things you never hear about. People are apt
to lie (not only to others but to themselves), they forget things, do not know things...
But observation shows the truth. 

*Advantages*: Experienced observer may pick some mission critical details.
This method is as objective, as possible. Observation results may lead to the whole problem re-evaluation. 
*Disadvantages*: It’s hard to organize observation well most of the time. Experienced
observers are rare. When improperly organized, observation gives a lot of “bad data”.

**Prototyping** allows to use “something real” (not imaginary) both as (and always
these two ways): a) the source of the new information; b) real material thing to
discuss.

*Advantages*: Most people prefer to see the object in discussion. No matter how
detailed the description is, real object provides more data.
*Disadvantages*: Prototyping takes time. Some work may be discarded after discussion.
It is crucial to do enough and stop, otherwise a lot of work may be wasted.

**Modeling** is somehow similar to prototyping, but it (usually) does not require
“physical” development. A model may be mathematical one, computational one and so on.

*Advantages*: Model makes a lot of difficult things easy and understandable. Model
allows to see hidden properties of some object / process. Model allows to see if
something is even possible / good.
*Disadvantages*: Modeling requires a lot of experience, knowledge, tools. Improper
model may give us bad data. Models are harder to understand than prototypes.

**Documentation analysis** allows us to find issues with existing project/product
documentation and to get extra information (when reading standards, manuals, books,
etc.)

*Advantages*: This method requires no special actions, tools, and so on: you may just
sit and read a document. Anytime you like. Anywhere you like. Reading documentation
makes you a better professional.
*Disadvantages*: Sometimes with new data new questions rise (you have to write them
down for further discussion). Working alone increases the probability to miss a
defect or to create one.

**Work with focus groups** looks a lot like questioning except it involves in-
person communication, discussions, end-user involvement in beta-testing, deep
end-user participation in product development.

*Advantages*: We can gather a lot of information from real end-users. Unlike
questioning this activity creates deep involvement. We may not only gather
information, but influence people opinion.
*Disadvantages*: Sometimes it’s difficult to gather a proper focus group. Experienced professional is required to organize the process. Some NDA issues may arise.

**Self-(re)writing** is mostly a way not for gathering requirements, but for
formalizing them (because it’s extremely difficult to think for the customer and
somehow telepathically know his ideas ☺).

*Advantages*: Each and every just mentioned way of requirements gathering provides
us with information that has to be re-worked, re-formulated, and included into
Requirements document. Self-(re)writing gives us that.
*Disadvantages*: Sometimes it’s difficult to avoid adding your own ideas into the
Requirements. You can propose ideas but absolutely have to get the approval from
the Customer side.

## Requirements Levels and Types

Requirements Levels:

- Business Requirements Level
    - Project Vision (is the document which usually contains the information on
      "where does the project end")

- User Requirements Level
    - Use-cases / user stories
      With **Use Cases** we usually have rather huge document with UML diagrams inside,
      with a lot of basic, alternative, exceptional scenarios, preconditions, and
      so on. Use Cases approach is typical for such software development models as
      Waterfall, V-model, Spiral model, Iterative-incremental model and so on. 
      With **User Stories** things are different, the typical formula for the User
      Story is: "As WHO, I want WHAT, so that WHY". For instance: "As a system
      administrator I want to select several items, so I can delete them all
      simultaneously". This approach is typical for Agile models like Scrum, Kanban,
      Lean and so on. 

- Functional Requirements Level

- Non-Functional Requirements Level

Software Requirements Specification (SRS)

**Business requirements** express the purpose for which the product is developed (why
is it needed at all, what benefits are expected from it).

**User requirements** describe the tasks that a user can perform with the system
(system response to user actions, user scenarios).

**Functional requirements** describe the behavior of the system, i.e. its actions
(calculations, transformations, checks, processing, etc.)

**Non-functional requirements** describe the properties of the system (usability,
security,reliability, extensibility, etc.) that it must possess when implementing
its behavior.

Requirements types:

- Functional requirement – a requirement that specifies a function that a component
  or system must be able to perform.

- Non-functional requirement – a requirement that describes how the component or
  system will do what it is intended to do.

## Good Requirements Properties

- Consistency
- Unambiguousness
- Atomicity
- Completeness
- Obligation 
- Up-to-date
- Traceability
- Modifiability
- Feasibility
- Ranked for...
  - Importance
  - Stability
  - Priority

### Atomicity

A requirement is **atomic** if it cannot be broken down into separate requirements
without loss of completeness, and it describes one and only one situation.

#### Typical problems Atomicity

- One requirement actually contains several independent requirements.
- The requirement allows discrepancies due to the grammatical features of
  the language.
- Description of several independent situations combined into one requirement.

#### How to detect typical problems Atomicity

Think, discuss with colleagues and use common sense. If we consider that a certain
section of requirements is overloaded and requires decomposition, most likely it
is so.

#### How to fix typical problems Atomicity

Process, re-write and structure the requirements: split them into sections, subsections, paragraphs, etc.

### Completeness

The requirement is **complete** if it provides all the necessary information, if
nothing is missed or left out for reasons such as “this is already clear to everyone”.

#### Typical problems Completeness

- There is no non-functional part of the requirement or link to the corresponding non-
  functional requirement (e.g.: “passwords must be stored in encrypted form” - what
  is the encryption algorithm?).
- Only a part of some enumeration is mentioned (e.g.: “export is carried out in PDF,
  PNG, etc. ”formats - what should we understand by “etc.”?).
- The references cited are ambiguous (e.g.: “see above” instead of “see section 123.45.b”).

#### How to detect typical problems Completeness

Most requirements testing techniques are applicable, but the best are: asking
questions and using graphical representations of the system being developed.

#### How to fix typical problems Completeness

Once we see that something is missing, it is necessary to obtain the missing
information and add it to the requirements. A little re-writing may be needed.

### Consistency

A **consistent** requirement should not contain internal contradictions and/or
contradictions with other requirements and documents.

#### Typical problems Consistency

- Contradictions within one requirement.
- Contradictions between two or more requirements, between a table and text, a
  picture and text, a requirement and a prototype, etc.
- Incorrect terminology or different terms to refer to the same phenomenon.

#### How to detect typical problems Consistency

Good memory helps best ☺, but tool for graphical representation of the system being
developed are also extremely useful.

#### How to fix typical problems Consistency

Once we detect an inconsistency, it is necessary to clarify the situation with the
Customer and make the necessary changes to requirements.

### Unambiguousness

A requirement is **unambiguous** (clear) if it is described without the use of jargon, non-obvious abbreviations and vague wording, and allows only one objective understanding.

#### Typical problems Unambiguousness

- Use of terms or phrases that allow subjective interpretation.
- Use of non-obvious or ambiguous abbreviations without decoding.
- Writing the requirement assuming that some parts are obvious to everybody by
  default and therefore needs no explanation.

#### Indicators of problems with unambiguousness

Adequate, be able to, easy, provide for, as a minimum, be capable of, effectively,
timely, as applicable, if possible, to be determined (TBD), as appropriate, if
practical, but not limited to, capability of, capability to, normal, minimize,
maximize, optimize, rapid, user-friendly, simple, often, usual, large, flexible,
robust, state-of-the-art, improved, efficient.

E.g. (real quotation):

“In case of necessity to optimize large files transfer, the app should effectively use
the minimum of RAM (if possible).”

#### How to detect typical problems Unambiguousness

Look for specific words and phrases. Writing check-lists is also effective: it is
hard to come up with a good check-list for a requirement that is ambiguous.

#### How to fix typical problems Unambiguousness

Use numbers and formulas instead of a verbal description. If this is not possible,
at least use the most accurate technical terms, references to standards, etc.

### Obligation and Up-to-date

Any requirement should be **obligatory and up-to-date**, otherwise (if the requirement
is not mandatory for implementation or is outdated) it should be removed.

#### Typical problems Obligation and Up-to-date

- The requirement was added for “why not” reason although there is no real need
  for it.
- The requirement has wrong values for priority/importance properties.
- The requirement is outdated, but it has not been removed.

#### How to detect typical problems Obligation and Up-to-date

Periodic review of requirements (preferably with the participation of the Customer)
allows you to notice fragments that have lost their obligation or have become
outdated ones.

#### How to fix typical problems Obligation and Up-to-date

Re-write requirements to eliminate fragments that have lost obligation or have
become outdated ones.

### Feasibility - осуществляемость

A **feasible** requirement is the one that technologically achievable and may be
implemented within the project budget and schedule.

#### Typical problems Feasibility

- So called “Gold plating” – requirements that are extremely expensive to
  implement and at the same time almost useless for end users.
- Requirements that are technically unrealistic at the present level of technology.
- Unrealizable requirements (usually – requirements not to the product, but to the
  user, environment, laws of physics and so on).

#### How to detect typical problems Feasibility

Use every bit of your subject matter experience to understand that a certain requirement
“costs” too much or is infeasible at all within current Projects limitations.

#### How to fix typical problems Feasibility

There is nothing else to do, but to discuss the situation with the Customer and either
change the requirement, or reconsider the terms of the Project (making this requirement
feasible).

### Traceability - прослеживаемость

**Vertical traceability** shows the connection between levels of requirements,
**horizontal traceability** shows the connection between a requirement and a test
plan paragraph, test cases, architectural solutions, etc.

#### Typical problems Traceability

- Requirements have no ids, not structured, don’t have a table of contents, don’t
  have cross-references.
- No tools and/or techniques of requirements management were used during the
  development of requirements.
- The set of requirements is incomplete, it is fragmented and has obvious “blind
  spots".

#### How to detect typical problems Traceability

Traceability problems mean no answers to questions like “where did this requirement
came from?”, “where are the related requirements?”, “what does it affect and what
is it affected by?”

#### How to fix typical problems Traceability

Re-work requirements: change the structure, arrange cross-references, add tags,
bookmarks, etc.

### Modifiability

**Modifiability** characterizes the ease of making changes to individual requirements
or to a set of requirements. With good modifiability changes go well without
unexpected side effects.

#### Typical problems Modifiability

- Requirements are non-atomic and/or untraceable, therefore changes lead to
  inconsistency.
- Requirements are initially contradictory, so changes (not related to eliminating
  inconsistencies) only worsen the situation.
- Requirements are in an inconvenient form (e.g., requirements management tools
  are not used, so the team has to work with dozens of huge text documents).

#### How to detect typical problems Modifiability

No traceability – no modifiability. Also, the modifiability decreases with the
violation of almost any “good requirement” property.

#### How to fix typical problems Modifiability

Re-write requirements with a primary goal is to increase the traceability. While doing
this, you can fix a lot of other problems with requirements.

### Importance, Stability, Priority

**Importance** shows how the success of the Project depends on the success of the
implementation of the requirement.
**Stability** shows the likelihood that in the foreseeable future the requirement
will not be changed.
**Priority** shows what requirements should be implemented earlier orlater.

#### Typical problems Importance, Stability, Priority

No rank (or incorrect rank, or outdated rank) for importance, stability, priority

#### How to detect typical problems Importance, Stability, Priority

Review requirements (with the participation of the Customer) to detect incorrect
values of importance, stability, and priority. Repeat such review periodically.

#### How to fix typical problems Importance, Stability, Priority

Make corrections during the review process.

**Correctness and verifiability** state that it is possible to create an objective
test case (test cases) that clearly shows that the requirement is implemented correctly
and the behavior of the application exactly corresponds to the requirement.

#### Typical problems

As these properties follow from compliance with all of the above mentioned ones,
if any other “good property” is violated the requirement most likely becomes
incorrect and unverifiable.

#### How to detect typical problems

Since we are dealing with an “integral problem”, we can use methods described earlier.
There are no unique techniques here.

#### How to fix typical problems

Make necessary changes to the requirements. Starting from simple typo correction,
and up to global re-writing of the entire requirement set.

## Requirements Testing Techniques

- Peer review - экспертная оценка
- Asking questions
- Writing check-lists
- Visualization
- Modeling and prototyping

### Peer review

**Peer review** – a form of review of work products performed by others qualified
to do the same work.

Types of peer review:

- Walkthrough - Quick feedback from colleagues

- Technical review - Review by a group of specialists (preferable with different
  skillsets)

- Formal inspection - Formal and systematical approach with a lot of specialists
  following special procedures

### Ask some questions

Bad requirement - “The app should start fast”
Bad questions:

- “How fast?” (What do you expect to hear? “Extremely fast”? “As fast as possible”?
  “Fast enough”?)
- “What if it wouldn't start fast?” (Do you really want to upset the Customer or
  even make him angry?)
- “Always?” (“Yes, always!” Did you expect some other answer?)

Good questions:

- “What is the maximum time to start and what hardware / OS are we talking about?
  How busy is the system with other tasks?”
- “Why is the start time so important? What is depending on it?”
- “May we start/load some components of the app in background?”
- “What state/conditions should we see as the mark that the app is started?”

### Writing check-lists

Ask yourself: “How shall I test this requirement? Are there tests that show objectively
that this requirement is implemented correctly?”

If you have a lot of ideas in mind – that’s good, but not enough: this requirement
may be outdated, inconsistent and so on.

If you have no ideas – that’s a reason to investigate this situation more thorough,
gather more info, ask questions.

### Visualization

Either to see the overall big picture or to drill into details you can use drawings,
diagrams, schemas, mind maps, concept maps, etc.

### Modeling and prototyping

Use mental simulation of the user experience, think about ambiguous or completely
undescribed options for the behavior of the system.

Prototyping and modeling may require special tools and knowledge, but it can save
a lot of time and effort.

https://github.com/craigtp/BookDigests/blob/master/BookDigests/SoftwareRequirements.md

https://www.slideshare.net/ahmedengu/software-requirements-3rd-edition-summary





