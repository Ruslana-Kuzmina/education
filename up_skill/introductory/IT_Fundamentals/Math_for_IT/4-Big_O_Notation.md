# Big O Notation

When it comes to analyzing the performance of an algorithm, we usually write a
function, say f(n), that represents the amount of time, the number of steps, or
the amount of space needed to complete a problem of size n. In this case, we are
not interested in the exact value of f for some particular n, but we are interested
in how fast f(n) is growing as n increases. In other words, we want to know the
**rate of growth** of the function f.

To describe the growth of functions as the input size increases, the so-called
**asymptotic notations** are used. They describe the limiting behavior of a function
when its argument tends towards infinity.

n -> infinity

We will start our discussion with one of such notations, **Big O notation** (capital
letter O, not zero), also called a Landau symbol. The letter O is used because
the rate of growth of a function can also be referred to as its order. On the example
of the running time of an algorithm, Big O is used as an asymptotic *upper bound*
on the running time.

Let f and g be two functions mapping natural numbers to positive real numbers. Then

f(n) = O(g(n))

(read as "f is big O of g") if there exists a real constant c>0 and there exists
a natural constant n0 such that

f(n)<=cg(n) for all n>=n0

We say that f grows at most as fast as g, or no faster than g.

The purpose of the condition n>=n0 is to ignore the behavior of f compared with g
when n is small.

When we write f(n)=O(g(n)), we do not use the equal sign in the usual mathematical
sense. Here, the equal sign means "is."

## Simplification Rules

To express the rate of growth of a function using Big O notation, the following
rules can be applied:

Rule 1. If the function f is represented as the sum of several terms, then the term
that grows faster than the others will determine the order of f. In other words,
when the argument of f tends to infinity, the term with the highest growth rate
starts to dominate making insignificant that contribution of the remaining terms
to the rate of growth of the entire function.

Rule 2. Factors that do not depend on the argument of a function, or simply
constants, can be dropped. That is, we do not write O(4n^3) despite the fact that
it does not violate the definition. Instead, we write O(n^3).

The goal is to keep g as simple as possible.

### How to choose the function g?

When representing f(n) as O(g(n)), the following typical functions are commonly
used as a function of g.

1<log2(n)<square root n<n<nlog2(n)<n^2<n^3<...<2^n<n!<n^n

This chain of inequalities does not hold for all values of n. It holds only for
n>=n0, where  is some sufficiently large number.

For a function f, select a function g such that O(g(n)) is the tightest upper bound.

## Related Asymptotic Notations

You have already learnt that Big O is used as an asymptotic upper bound of a function.
Along with an upper bound, we can determine an asymptotic *lower bound* of a function.
For this purpose, Big Omega notation is used.

### Big Omega

Let f and g be two functions mapping natural numbers to positive real numbers. Then

f(n) = Om(g(n))

(read as "f is Big Omega of g") if there exists a real constant c>0 and there exists
a natural constant n0 such that

f(n)>=cg(n) for all n>=n0

We say that  grows at least as fast as .

The only difference between Big O and Big Omega is the inequality sign between f(n)
and cg(n).

When a function f(n) is both O(g(n)) and Om(g(n)), we say that f(n) is Big Theta
of g(n), or Theta(g(n)).

#### Big Theta

Let f and g be two functions mapping natural numbers to positive real numbers. Then

f(n)=Theta(g(n))

(read as "f is Big Theta of g") if there exist real constants c1,c2>0 and there
exists a natural constant n0 such that

c1g(n)<=f(n)<=c2g(n) for all n>=n0

We say that f grows at the same rate as g.

Note that c1<=c2 and n0 = max{n1, n2}, where n1 and n2 are the corresponding
constants of Big O and Big Omega definitions.

Equivalently,f(n) = Theta(g(n)), if f(n) is both (g(n)) and Omega(g(n)).

To prove that a function f is Big Theta of g, we need to prove separately that
f is Big O of g and is Big Omega of g.

##### Little Asymptotic Notations

Asymptotic notations are not always Big. Next, we will consider two asymptotic
notations that are little.

Little O

Let f and g be two functions mapping natural numbers to positive real numbers. Then

f(n) = o(g(n))

(read as "f is little o of g") if for any real constant c>0 there exists a natural
constant n0 such that

f(n)<cg(n) for all n>=n0

We say that f grows slower than g.

The difference between Big O and little o is that the latter makes a stronger
statement than the former. The definition of Big O requires the inequality to be
true for at least one constant c, while the definition of little o requires the
truth of the inequality for any constant c. Because of this,

f(n)=o(g(n)) -> f(n)=O(g(n))

while the converse is not true.

Little Omega

Let f and g be two functions mapping natural numbers to positive real numbers. Then

f(n)=little omega(g(n))

(read as "f is little omega of g") if for any real constant c>0 there exists a
natural constant n0 such that

f(n)>cg(n) for all n>=n0

We say that f grows faster than g.

Compared to Big Omega, little omega makes a stronger statement for the same reason
as little o is a stronger statement than Big O. Because of this,

f(n)=little omega(g(n)) -> f(n)=Omega(g(n))

while the converse is not true.

## Asymptotic Notations and Limits

### Limit Method

Suppose we have two functions f and g that depend on n. Then, to compare the rates
of growth of these functions, we need to determine the limit of f/g as n approaches
infinity.

Lim f(n)/g(n) n -> infinity

Asymptotic relationship between f and g depending on the value of the limit

=0
f(n)=o(g(n))
f(n)=O(g(n))

>0 and =/ infinity
f(n)=Theta(g(n))
f(n)=O(g(n))
f(n)=Omega(g(n))

= infinity
f(n)=little omega(g(n))
f(n)=Omega(g(n))
