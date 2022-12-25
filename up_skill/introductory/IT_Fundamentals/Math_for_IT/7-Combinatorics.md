# Combinatorics

## Additive and Multiplicative Principles

The Additive Principle (or Rule of Sum) and Multiplicative Principle (or Rule of
Product) are the basic principles of counting in combinatorics.

Consider two disjoint or mutually exclusive events A and B.

That is, these two events cannot happen at the same time.

### Additive Principle

If event A can occur in m ways, and disjoint event B can occur in n ways, then
the event "A or B" can occur in m+n ways.

Generalization of Additive Principle

If a sequence of disjoint events A1,A2,...An can occur in m1,m2,...mn ways
respectively, the event "A1 or A2 or ... An" can occur in m1+m2+...+mn ways.

#### Multiplicative Principle

Now, consider two events A and B that are independent.

That is, the occurrence of one event does not affect the occurrence of the other
one. Then, the multiplicative principle can be formulated as follows:

If event A can occur in m ways, and independent event B can occur in n ways, then
the event "A and B" can occur in m*n ways.

Generalization of Multiplicative Principle

If a sequence of independent events A1,A2,...An can occur in m1,m2,...mn ways
respectively, the event "A1 and A2, ... amd An" can occur in m1*m2*...mn ways.

## Permutations

A permutation is an arrangement of objects when order is important.

Factorial

The factorial of positive integer n, denoted by n!, is the product of all positive
integers less than or equal to n.

n!=n*(n-1)*(n-2)*(n-3)*...*3*2*1

According to the convention, 0!=1.

Permutations of n Elements

For n distinct elements, the number of permutations is n!.

k-permutations of n Elements

P(n,k), the number of k-permutations of n elements (k<=n), is the number of ways
to arrange k distinct elements chosen from n non-repeated elements.

P(n,k)=n*(n-1)*(n-2)*...*(n-k+1)=n!/(n-k)!

When n=k, we have P(n,k)=n!/(n-n)!=n!/0!=n!/1=n!

## Combinations and the Binomial Theorem

A combination is a selection of objects when order is not important.

k-combinations of n Elements

C(n,k), the number of k-combinations of n elements (k<=n), is the number of ways
to select k distinct elements from n non-repeated elements.

C(n,k)=P(n,k)/k!=n!/(n-k)!*k!=(n)
                              (k)

The number of the form (n)
                       (k) is referred to as Binomial Coefficient and read as
"n choose k." The binomial coefficients are called this way because they are the
coefficients of the binomial expansion.

The Binomial theorem provides general formula for expanding (x+y)^n.

## Pascal’s Triangle and Pascal’s Identity

The coefficients of the binomial expansions form a pattern called "Pascal's triangle."

One of the important Binomial identities that follows from Pascal's triangle is
called Pascal’s identity or Pascal's formula.

Pascal’s Identity

For any integer n>=0 and for any integer 0<=k<=n,

(n)=(n-1)+(n-1)
(k) (k-1) (k)

## Permutations and Combinations with Repetition

### Permutations with Repetition

k-permutations of n Elements with Repetition
If repetition is allowed, the number of k-permutations of n non-repeated elements
equals n^k.

#### Combinations with Repetition

For integers k>=0 and n>=0, the number of ways to select k elements from n non-repeated
elements, or the number of k-combinations of n, when repetition is allowed, is

C(k+n-1, k)=C(k+n-1, n-1)=(k+n-1)!/(n-1)!*k!

For k stars and  n-1 bars, there are k+n-1 places in total. The goal is to choose
where to put k stars (the remaining n-1 places will be bars), or where to put n-1
bars (the remaining k places will be stars).

