# Introduction to Defect Hunting and Reporting

- Defects and Defect Reports.
- Defect Report Fields.
- Typical Defect Reporting Mistakes.
- Defect Reporting Recommendations.
- Defect Reports Sample.

## Defects and Defect Reports

**Defect** – an imperfection or deficiency in a work product where it does not meet
its requirements or specifications.

**Expected result** – the predicted observable behavior of a component or system
executing under specified conditions, based on its specification or another source.

**Actual result** – the behavior produced/observed when a component or system is
tested.

Error, Mistake --> Defect, Problem, Bug, Fault --> Failure, Interruption
    |                           |                            |
                   Anomaly, Incident, Deviation

**Anomaly, incident, deviation** – any deviation of the observed (actual) result,
state, behavior, value, property from the observer's expectations, formed on the
basis of requirements, specifications, other documentation or experience and common
sense.

**Defect report** – documentation of the occurrence, nature, and status of a defect.

A defect report should:

- Describe the issue in details 
- Define the severity and priority of the issue
- Provide all necessary data to reproduce and fix the issue
- Help developer to fix the issue

Bad defect report:

- Lacks significant details
- Takes time to understand
- Forces the developer to re-do testers work

Good defect report:

- Provides significant details
- Easy and obvious
- Facilitates quick and easy solutions

Before you write down a defect report, make sure you have answers to the following
questions:

What have I done? --> Steps to reproduce
What have I got? --> Actual result
What did I expect to get? --> Expected result

Defect Report Lifecycle

Submitted --> Assigned --> Fixed --> Verified --> Closed
    |                        |
Deffered                  Reopened
                             |
                        To be declined
                             |
                          Declined

### Defect Report Fields

- ID
- Summary
    - Answers questions: **what** did happen, **where** did it happen, and in **what**
      **conditions** did it happen.
    - Should at the same time:
        - Provide as much information as possible.
        - Be as short as possible.
        - Be easily distinguishable from other summaries.
- Description
    - Contains detailed defect description.
    - Unlike Summary, Description may be long enough.
    - In many BTS testers use Description to write down the actual result, the
      expected result and the reference to the corresponding requirement.
- Steps to reproduce
    - Contains detailed description of actions to be done to reproduce the defect.
    - May contain a short description of the defect or the final erroneous state
      of the application.
- Reproducibility
    - Shows if the defect appear each time we follow steps to reproduce (“always”),
      or if the defect sometimes appears and sometimes doesn’t (“sometimes”).
    - Defects with the reproducibility “always” are much more easy to fix.
- Severity
    - Shows the damage the defect causes.
    - Typical values are:
        - Critical
        - Major
        - Medium
        - Minor
- Priority
    - Shows the urgency to fix the defect.
    - Typical values are:
        - ASAP
        - High
        - Normal
        - Low
- Symptom
    - Allows defects classification by typical indication:
        - Cosmetic flaw.
        - Data corruption/loss.
        - Documentation issue.
        - Incorrect operation.
        - Installation problem.
        - Localization issue.
        - Missing feature.
        - Scalability issue.
        - Low performance.
        - System crash.
        - Unexpected behavior.
        - Unfriendly behavior.
        - Variance from specs.
        - Enhancement.
- Workaround
    - Shows, if there is a way to achieve the desired result without being interrupted
      by the defect.
    - Typical values are: “yes”, “no”.
- Comments
    - Optional field.
    - May contain any data useful to the process of bug fixing.
- Attachments
    - Optional field.
    - May contain any files, screenshots, etc. useful to the process of bug fixing.

Severity - Shows, **how dangerous** the defect is

Priority - Shows, **how quickly** the defect should be fixed

#### Typical Defect Reporting Mistakes

- Not enough information to understand and reproduce the defect.

- The “defect” is found in a functionality not yet marked as “ready for testing”.

- Any field contains wrong information (for any reason – copy-paste issues,
  misunderstanding, inattentiveness, etc...)

- A defect report contains slang or strong words.

- A defect report contains criticism to someone's work.

- Some critical details (e.g. the environment specifics) are missing in the report.

- A defect report has inappropriate severity/priority values.

- A defect report is written messy, illiterately, confusingly.

- Necessary logs, screenshots, etc. are missing from the report.

- The tester didn’t manage to convince the team about the defect consequences.

Most mistakes come from the inattentiveness. So be careful, re-read your defect report.

Try to see the technical background, the real cause of the defect. Don’t stop at
the interface behavior only.

The more “tricky” defect you found, the more time it may take to deal with. But
it saves much more time in the future.

##### Defect Reporting Recommendations

- Describe the STR with even the smallest details.
- Add details no only to STR, but to all other fields
- Write down every detail, don’t rely on the “esoteric” knowledge.
- Reference to the requirement the defect violates.
- Provide key details explicitly!
- Even if your BTS doesn’t provide such feature, name the environment the defect
  found within.
- Don’t be emotional. Even if you consider the defect to be someone’s epic fail,
  just provide details, not your opinion.
- Write separate defect report for each found defect. Don’t combine several defects
  into one defect report.
- Make the root cause analysis. Try to find the real cause of the defect. Don’t
  stop with only system behavior description.
- If you have enough technical experience, provide a recommendation on how to fix
  the defect.
- Write down the defect report immediately once you found it and performed all the
  necessary actions (like root cause analysis, checking the BTS for duplicates
  and so on).
- The less time has passed, the more details you remember.
- The sooner the defect report appears, the sooner someone starts working on the defect.
- Analyze the most critical consequences of the defect. This information will not
  only help with Severity and Priority fields, but may lead you to some useful
  ideas on additional tests.