# Probability Theory

## Basic Terminology

An **experiment** is a planned operation carried out under controlled conditions.
If the result is not predetermined, then the experiment is said to be a **chance**
**experiment**.

### Outcome and Sample Space

The result of an experiment is called an **outcome**. The **sample space** of an
experiment is the set of all possible outcomes. To denote the sample space,
the uppercase letter S is used.

For example, if we flip one fair coin, the sample space is S={H,T}, where H=heads
and T=tails are the outcomes.

An **event** is any combination of outcomes. To represent events, we use uppercase
letters, like A and B. For example, if the experiment is to flip one fair coin,
event A might be getting at most one head. The probability of an event A is written
P(A).

A **frequency** is the number of times a value of the data occurs.
A **relative frequency** is the ratio (fraction or proportion) of the number of
times a value of the data occurs in the set of all outcomes to the total number
of outcomes. In other words, to find a relative frequency, we divide a frequency
by the total number of outcomes.

The **probability** of any outcome is the **long-term relative frequency** of that
outcome.

Probabilities are between zero and one, inclusive (that is, zero and one and all
numbers between these values).

P(A)=0 means the event A can never happen.
P(A)=1 means the event A always happens.
P(A)=0,5 means the event A is equally likely to occur or not to occur.

**Equally** likely means that each outcome of an experiment occurs with equal
probability. For example, if we toss a fair, six-sided die, each face
(1, 2, 3, 4, 5, or 6) is as likely to occur as any other face. If we toss a fair
coin, a Head (H) and a Tail (T) are equally likely to occur. If we randomly guess
the answer to a true/false question, we are equally likely to select a correct
answer or an incorrect answer.

The **law of large numbers** states that as the number of repetitions of an experiment
is increased, the relative frequency obtained in the experiment tends to become
closer and closer to the theoretical probability. Even though the outcomes do not
happen according to any set pattern or order, overall, the observed long-term relative
frequency will approach the theoretical probability. (The word empirical is often
used instead of the word observed.)

It is important to realize that in many situations, the outcomes are not equally
likely. For instance, a coin or a die may be **unfair**, or **biased**.

"OR" Event

An outcome is in the event A OR B if the outcome is in A or is in B, or is in both
A and B. For example, let

A={1,2,3,4,5}
and
B={4,5,6,7,8}

Then, A OR B={1,2,3,4,5,6,7,8}
Note that 4 and 5 are NOT listed twice.

"AND" Event

An outcome is in the event A AND B if the outcome is in both A and B at the same
time. For example, again, let

A={1,2,3,4,5}
and
B={4,5,6,7,8}

Then, A AND B={4,5}

Complement of an Event

The complement of event A is denoted A' (read " A prime"). A' consists of all
outcomes from the sample space that are not in A. Note that

P(A)+P(A')=1

For example, let

S={1,2,3,4,5,6}
A={1,2,3,4}

Then, A'={5,6}.

P(A)=4/6
P(A')=2/6
P(A)+P(A')=4/6+2/6=1

#### Conditional Probability

The conditional probability of A given B is written P(A|B).

P(A|B) is the probability that event A will occur given that event B has already
occurred.

P(A|B)=P(A AND B)/P(B), P(B)>0

A conditional reduces the sample space. In other words, we calculate the probability
of A from the reduced sample space B.

## Independent and Disjoint Events

### Independent Events

Two events are independent if the following are true:

P(A|B)=P(A)
P(B|A)=P(B)
P(A AND B)=P(A)*P(B)

Two events A and B are **independent** if the knowledge that one of them occurred
does not affect the chance for the other one to occur.

If two events A and B are NOT independent, then we say that they are **dependent**.

To show that two events are independent, we must show **only one** of the above conditions.

**Population** is a collection of persons, things, or objects under study. To study
the population, we select a **sample**. The idea of sampling is to select a portion
(or a subset) of the larger population and study that portion (the sample) to gain
information about the population. Data are the result of sampling from a population.

Sampling may be done with replacement or without replacement.

- With Replacement
  If each member of a population is replaced after it has been picked, then that
  member has the possibility of being chosen more than once. When sampling is done
  with replacement, then the events are considered to be independent, which means
  the result of the first pick will not change the probabilities for the second pick.

- Without Replacement
  When sampling is done without replacement, each member of a population may be
  chosen only once. In this case, the probabilities for the second pick are affected
  by the result of the first pick. The events are considered to be dependent or not
  independent.

If it is not known whether A and B are independent or dependent, assume they are
dependent until you can prove otherwise.

#### Disjoint Events

Two events A and B are **disjoint** or **mutually exclusive** if they cannot occur
at the same time. This means that A and B do not share any outcomes, and
P(A AND B)=0.

For example, suppose that the sample space is S={1,2,3,4,5,6,7,8,9,10}

and let

A={1,2,3,4,5}
B={4,5,6,7,8}
C={7,9}

The event A AND B={4,5}, and P(A AND B)=2/10=/0. Therefore, the events A and B are
not disjoint.

The events A and C do not have any numbers in common, so P(A AND C)=0. Therefore,
the events A and C are disjoint.

If it is not known whether A and B are mutually exclusive, assume they are not
until you can prove otherwise.

## Multiplication and Addition Rules

### The Multiplication Rule

If A and B are two events defined on a sample space, then

P(A AND B)=P(A|B)*P(B)

or, alternatively,

P(A|B)=P(A AND B)/P(B)

If A and B are independent, then P(A|B)=P(A). Therefore, P(A AND B)=P(A|B)*P(B)
becomes P(A AND B)=P(A)*P(B).

#### The Addition Rule

If A and B are two events defined on a sample space, then

P(A OR B)=P(A)+P(B)-P(A AND B)

If A and B are disjoint, then P(A AND B)=0. Therefore,
P(A OR B)=P(A)+P(B-P(A AND B) becomes P(A OR B)=P(A)+P(B).





