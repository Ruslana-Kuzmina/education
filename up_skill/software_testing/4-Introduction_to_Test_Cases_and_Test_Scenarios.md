# Introduction to Test Cases and Test Scenarios 

- Checklists.
- Basic Testing Techniques.
- Test Cases.
- Good Test Cases Properties.
- Test Suites.
- Checklists, Test Cases, Test Suites Samples.
- How to focus on Important Things in Testing.
- How to improve your Test Cases with only four questions.

## Checklists

Checklist – a set of ideas.

In testing checklists come first: this is a kind of draft for further activities.
Writing and re-writing checklists is (relatively) fast and simple. When checklist
is ready (and reviewed by colleagues) each item may become a source for one or several
test cases.

Write down your checklists! - This prevents you from forgetting any ideas and allows
you to easily share and re-use a lot of checklists.

Start with simple ideas! - It is recommended to start with ideas of simple tests
to check basic functionality and/or user scenarios. Don’t try to check rare extreme
cases until you’re done with simple and obvious ones.

Checklists writing approaches:

- By application parts, sub-parts, sub-sub-parts
- By user scenarios and actions
- By subject matter scenarios and cases
- By testing objectives and quality criteria
- By requirements
- By interface

### Basic Testing Techniques

An **equivalence class** consists of a set of data that is treated the same by a
module or that should produce the same result.

The **boundaries** — the “edges” of each equivalence class.

So we have to find out which input data is treated the same way and use boundary
values technique to select values to test.

Functional approach

#### Test Cases

**Test case** – a set of preconditions, inputs**, actions (where applicable),
expected results and postconditions, developed based on test conditions. Test
case always follows some purpose.

These four parts are crucial for a good test case:

- inputs
- actions
- expected results
- purpose

Key test case fields: 

- ID
    - Unique
    - Meaningful (if test management tool allows)
- Priority
    - Shows how important this test case is.
    - Represented by letters (A, B, C, D, E), numbers (1, 2, 3, 4, 5), words
      («extremely high», «high», «medium», «low», «extremely low») or any other
      convenient way.
    - Correlated with:
        - the requirement importance;
        - potential severity of a defect that this test case may detect.
- Related Requirement
    - Contains the ID of the requirement this test case is intended to test.
    - Facilitates traceability between requirements and test cases.
- Module and submodule
    - Shows the application (sub)parts covered by the test case.
    - Simplifies understanding of test case purpose.
    - Module and submodule are **parts** of the application, *NOT actions*! See the
      difference (using human as example): «respiratory system, lungs» – module
      and submodule, but «breathing», «snuffling», «sneezing» – are NOT; «head,
      brain» – module and submodule, but «nodding», «thinking» – are NOT.
- Test case title
    - Shows the main idea (purpose) of the test case.
    - Populates the test cases list.
    - Is one of the main data sources when searching for a particular test case.
    - *A test case should ALWAYS have a title!*
- Necessary preparations (if any)
    - Is optional.
    - Describes actions and conditions to be done or met before the test case
      itself begins.
    - Often does not interfere with the application under test (unlike “Steps” data).
- Steps and expected results (for each step)
    - Steps describe action sequence to perform during the test case execution.
    - Expected results describe the application reaction to the specific input or
      action.
    - Both steps and expected results have the same numeric ids.

Useful ideas

- Use active voice and simple phrases in steps section
- Use objective description in expected results section
- Write simple, this is not a fiction novel
- Use exact names for interface elements
- Don’t explain basics

##### Good Test Cases Properties

And there are more specific properties:

- Somewhere between...
    - too specific
    - too general
- Somewhere between...
    - too simple
    - too complex
- Either... or...
    - independent
    - reasonably linked

Too specific:
- the probability of detecting an error is reduced due to re-executing exactly the
  same actions;
- the time of creation and support of the test case increases.

Too general:
- it’s difficult for beginners (or new people on the project) to understand such
  test cases;
- even huge effort to understand the initial idea may leave some gaps.

A **simple test case** operates with single object (or the main object is obvious),
it contains a small number of trivial actions.

A **complex test case** operates with several equal objects and/or contains many
nontrivial actions.

Simplicity: 

Pros:

- Easy to understand
- Easy to execute
- Easy to see the defects
- Found defects are obvious

Cons:

- Too simple test cases are nothing more than a step (or several steps) of more
  complex test cases. That’s why such extremely simple test cases are useless.

Complexity: 

Pros:

- More chances to break something
- More similar to real user actions
- Developers rarely test such things

Cons:

- Too complex test cases take a lot of time to write and maintain. And they often
  need huge maintenance with each application change.

It’s recommended to move from simple test cases to complex ones during the testing
process.

An **independent test case** to not reference to any other test case and is not
referenced by any other test case.

A **linked test case** either references to some other test case(es), or has a
fixed place in a chain of test cases.

Independency

+ Easy to execute in any order or set 
+ Easy to combine into sets/scenarios
+ Work if some other test cases fail

- Usually need more preparations
- Usually need more steps
- May produce some redundancy

Being linked

+ Usually need less preparations 
+ Usually need less steps
+ Start work from the point where previous test case ends

- The structure is fixed and rigid
- More difficult to maintain
- If previous test case fails, all next-in-chain test cases fail too

Independent test cases are industrial standard

Useful Idea:

- A good test case exposes some defect with high probability
- A good test case follows its goals without retreat
- A good test case does not contain unnecessary steps
- A good test case is not redundant with other test cases
- A good test case makes found defects obvious
- A good test case performs some non-trivial actions

###### Test Suites

**Test Suite** – a set of test cases or test procedures to be executed in a specific
test cycle.

Usually test suites are sets of test cases selected with some common goal or on
some common basis.

The main idea here is to manage testing process, to organize huge number of test
cases into small convenient sets.

When composing test suites, we may use any common sense. I.e. we may compose a test
suite with test cases that...

- Cover the same requirements section
- Have the same priority, module/submodule/etc...
- Work with the same functionality (e.g. FS, DBMS)
- Cover some user scenario or typical set of actions

**Free set** of test cases doesn’t imply any specific execution order, it only
composes several test cases together.

**Linked set** of test cases implies specific execution order.

Free

+ Easy to compose
+ Easy to change execution order
+ Still work if some test cases fail

- Hard to emulate user scenarios
- May produce some redundancy

Linked

+ Need less preparations and steps
+ Continues work from the point where previous test case ends
+ Easy to emulate user scenarios

- If previous test case fails, all next-in-chain test cases fail too

