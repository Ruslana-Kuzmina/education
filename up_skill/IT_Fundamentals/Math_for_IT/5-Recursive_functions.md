# Recursive Functions

## Recursively Defined Functions

When we talk about an object that is defined in terms of itself, the term recursion
occurs. Particularly, in mathematics as well as in programming, a recursive function
is a function that is defined in terms of a simpler version of itself.

A recursive function consists of two parts:

- Base case
  There can be one or more base cases. A base case gives the output value which
  the function returns for some specified input value. Note that the base case does
  not use recursion.

- Recursive formula

Consider the function you are already familiar with, the factorial function n!.

The factorial function n!

n!=n*(n-1)*(n-2)*(n-3)*...*3*2*1

n! is defined for all integers n>=0.

According to the convention, 0!=1.

Alternatively, we can define this function using recursion.

0!=1  Base case
n!=n*(n-1)! for all integers n>0 Recursive formula

To evaluate a function defined recursively, we successively unwind the recursive
formula until we hit the base case.

## Closed Forms of Recursively Defined Functions

Many recursively defined functions have an equivalent **closed-form function**, a
function that is defined without recursion.

Fr(0)=3
Fr(n)=Fr(n-1)+5 for n>0    Recursive function

Fc(n)=3+5n for n>=0   Closed-form function

Comparing the output values of the functions for different input values, we can
conclude that the recursively defined function Fr is equivalent to the closed-form
function Fc. You are probably wondering how to find an equivalent form for a recursively
defined function. And why would we need a closed form anyway? We will discuss this
further.

Why might closed-form functions be useful?

- To evaluate a closed-form function, say h(n), we just need to substitute a
  particular input value into the function formula and calculate. We do not need
  to refer to the previous function values h(n-1), h(n-2), … compared to recursive
  functions.

- To determine the running time of a recursive algorithm, we need to write a recursive
  function that describes the running time, to find an equivalent closed-form
  function, and express the limiting behavior of that function using Big-O notation.
  For example, we can easily say that Fc is On, while for Fr(n) this is not obvious.

The next thing we discuss is how to find an equivalent closed-form function for
a recursively defined function. We will consider the procedure called
**repeated substitution** or **iterative substitution**.

### Method of Repeated Substitution

To find a closed-form function for a given recursive function using the repeated
substitution method, perform the following steps:

- Substitute the recursive function into itself several times to reveal the pattern.

- Guess what the recurrence formula will look like after  substitutions.

- Find the value of  for which the function argument will hit the base case.

- Substitute the value of  into the formula from Step 2 and simplify to get the
  closed form.

- The closed form obtained in Step 4 is just our guess. So, the final step is to
  prove the correctness of this form using induction.

#### Mathematical Induction

Mathematical induction is a proof technique used to prove that a statement P(n)
is true for all natural numbers n>=a, sometimes including zero. Here, a can be 0,
1, or any fixed natural number.

A proof by induction consists of two steps or cases:

- Base case
  Show that a statement P(n) is true for n=a.

- Induction step
  For any arbitrary n=k, show that if P(k) is true, then P(k+1) is also true.
  Assume that P(k) is true (Induction hypothesis).
  Prove that P(k+1) is true under the assumption.

If these two steps hold, then P(n) is true for all n>=a.

The induction that we discussed is the so-called **simple or weak induction**. Looking
ahead, note that we will use this particular type of induction for our example. Apart
from weak induction, the so-called **complete or strong induction** is distinguished.
Weak and strong inductions are similar except for the difference in the induction
step.

Weak Induction
If P(k) is true, then P(k+1) is true.

Strong Induction
If P(i) is true for all i greater than or equal to a (base case) and less than or
equal to k, then P(k+1) is true.






