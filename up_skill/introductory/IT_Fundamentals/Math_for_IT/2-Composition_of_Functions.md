# Composition of Functions

## Definition of a Composite Function

Suppose we want to calculate a monthly salary of an employee who works 40 hours
per week on an hourly rate. The salary will depend on the number of hours worked,
and the number of hours worked, in turn, will depend on a month. Hence, we have
just defined two relationships: the monthly salary depends on the number of working
hours, and the number of working hours depends on a month.

Using the descriptive variables, we can write these functions as follows:

S(h) - The function that gives a monthly salary for the number of working hours

h(m) - The function that gives the number of working hours in a month

Salary = S(h(m)) - For any considered month, this means that the salary depends
on the hours worked, which in turn, depend on a month.

To determine the monthly salary, we create a new function that takes the month m
as an input and gives the salary S as an output. The process of combining functions
so that the output of one function becomes the input of another one is known as
the **composition of functions**. The resulting function is known as a **composite**
**function**.

When the output of one function is used as the input of another one, the entire
operation is called the composition of functions. For any input *x* and functions
*f* and *g*, this action defines a composite function, which is written as *f*g*
such that

(f*g)(x) = f(g(x))

The left-hand side of the equation is read as "f composed with g at x," and the
right-hand side of the equation is read as " f of g of x." The open circle
symbol * is called the composition operator.

The domain of the composite function  f*g is all x such that x is in the domain
of g and g(x) is in the domain of f.

In f(g(x)), the function g is called the "inside" function and the function f is
called the "outside" function.

There are two important points to consider:

- Function composition is not the same as function multiplication because in
  general, f(g(x)) = / f(x)g(x) .

- Function composition is not commutative, that is, in many cases f(g(x)) =/ g(f(x))
  for all x. Further, we will consider an example that illustrates this fact.

## Evaluating a Composite Function

We will consider functions represented as tables, graphs, and formulas.
We evaluate the inside function first and then use the output of the inside function
as the input to the outside function.

g(4) = 6
f(g(4)) = f(6) = 4

## Domain of a Composite Function

The domain of a composite function f(g(x)) is the set of those inputs x in the
domain of g for which g(x) is in the domain of f.

To find the domain of a composite function f(g(x)), perform the following steps:

- Find the domain of g.

- Find the domain of f.

- Find those inputs x in the domain of g for which g(x) is in the domain of f.
  In other words, from the domain of g, exclude those inputs x for which g(x) is
  not in the domain of f. The resulting set is the domain of f(g(x)), or f*g.

## Decomposition of a Composite Function









