# Math for IT

## Functions

- Decide whether the following relation represents a function.
  {(3,-3),(2,-2),(1,-1),(0,0),(1,1),(2,2),(3,3)}

Answer: The given relation is not a function because all input values except for
0 have two output values: 3 corresponds to both −3 and 3, 2 corresponds to
both −2 and 2, and 1 corresponds to both −1 and 1.

- Decide whether the following relation represents a function.
  {(-3,-27),(-2,-8),(-1,1),(0,0),(1,1),(2,8),(3,27)}

Answer: The given relation is a function because each input value corresponds to
exactly one output value.

- Decide whether the following relation represents a one-to-one function.
  {(-3,3),(-2,2),(-1,1),(0,0),(1,1),(2,2),(3,3)}

Answer: The given relation is a function but not a one-to-one function. Each output
value, except for 0, corresponds to two input values.

- Is it appropriate to write *y = y(x)* instead of *y = f(x)*, that is, to use
  the same letter for both a function and an output?

Answer: The answer is yes. You can face such a notation in applied subjects that
use higher math, such as physics and engineering. However, in studying math itself,
it is more convenient to distinguish between a function f, which is a rule or a
process, and the output y which we get by applying f to a particular input x. This
is why we usually use notations such as y = f(x), s = g(t), and so on.

- The functiont B = f(t) gives the account balance in dollars t days after a salary
  has been credited. What does f(15) = 1000 mean?

Answer:
The notation B = f(t) tells us that B, balance, is the result of application of the
rule f to t, the number of days. That is, t represents the input value and B represents
the output value. Therefore, f(15) = 1000 means that 15 days after the salary has
been credited, the balance is 1000 dollars.

- Represent the following statement using function notation.
  "the cost of a car is a function of mileage"

Answer: Let C denote the cost of a car, m denote mileage, and f denote the rule
that transforms mileage to cost. Then, the statement “the cost of a car is a function
of mileage” can be represented as C = f(m).

## Combinatorics

- In honor of her birthday, an online shoe store gave Hanna a 25% discount on one
  pair of shoes. Hanna researched the store's assortment and found out that there
  were 17 models of sneakers, 7 models of espadrilles, and 14 models of ankle boots
  of the appropriate size. How many purchase options does Hanna have?

Using the additive principle, the answer is 17+7+14=38 purchase options.

- Albert wants to buy a new office chair. He has already decided on the model but
  has not yet chosen a design. The backrest is available in 5 colors and 3 materials.
  The chair seat, in turn, is available in 4 colors and 2 materials. How many designs
  are available to Albert? Suppose that the choice of the color and material of
  the backrest and the choice of the color and material of the chair seat are not
  related.

Using the multiplicative principle, there are 5*3*4*2=120 possible designs.

- Jessica is planning an evening at the spa. She is making a choice between a complex
  with a foot and head massage and a complex with a back massage. Foot massage is
  available in 5 techniques, head massage in 3 techniques, and back massage in 4
  techniques. How many options does Jessica have to choose from?

Combining the multiplicative and additive principles, the answer is 5*3+4=19 options.

- Imagine that you have purchased a trial week at a foreign language school. The
  school offers three types of lessons: face-to-face lessons, lessons in small
  groups of 5 people, and speaking clubs in groups of 20 people. In a week, you
  need to try all these three types of lessons. Determine the number of ways to
  visit these three types of lessons.

Using factorial rule, the answer is 3!=3*2*1=6.

- Consider the word PROJECT. How many different 3-letter words can you form from
  this word? Suppose that a "word" is just a string of non-repeating letters.

Answer: P(7,3)=7!/(7-3)!=7*6*5=210

- Kelly is going to spend her vacation in city X. Kelly has found 11 landmarks
  she would like to visit in this city. However, due to time limitations, she will
  only have time to visit 6 of them. Count the number of ways Kelly can make a
  sightseeing program. Note that the order of visiting landmarks is important
  for Kelly.

Answer: P(11,6)=11!/(11-6)!=11*10*9*8*7*6=332640

- John is a master’s student. In the second year, there are 7 courses available
  to him and he must choose 3 of them. In how many ways can he do this if the
  order of courses is not important now?

Answer: C(7,3)=P(7,3)/3!= 7!/(7-3)!*3!=7*6*5*4*3*2*1/4*3*2*1*3*2*1=35

- Lara Johnson is a physical education teacher in a class with 13 boys and 11 girls.
  To participate in the competition, she needs to choose 3 boys and 4 girls. In
  how many ways can Lara Johnson do this if the order of selection is not important?

Answer: C(13,3)*C(11,4)=P(13,3)/3!*P(11,4)/4!=13*12*11/3*2*1 * 11*10*9*8/4*3*2*1=
13*2*11 * 11*10*3=286*330=94380

- There are 12 students in a class. For a laboratory work, a teacher needs to form
  pairs. In how many ways can he/she do this?

Answer: C(12,2)*C(10,2)*C(8,2)*C(6,2)*C(4,2)*C(2,2)/6!=P(12,2)/2!*P(10,2)/2!*
P(8,2)/2!*P(6,2)/2!*P(4,2)/2! * P(2,2)/2! /6!= 12*11/2 * 10*9/2 * 8*7/2 * 6*5/2*
*4*3/2 * 2/2 /6*5*4*3*2*1= 66*45*28*15*6/6*5*4*3*2*1=33*45*7=10395

- Consider the binomial (x+y)^19. Determine the coefficient before the term x^7*y^12.

Answer: The coefficient before x^7*y^12 is equal to C(19,7)=C(19,12)=50388.

- Consider the word LOGIC. How many different three-letter words can you form from
  this word? Suppose that a “word” is just a string of letters. Note that letters
  in a string can be repeated.

Answer: 5^3=125

- Paul wants to set a password on his suitcase lock. If the suitcase is equipped
  with a three-digit password lock, how many password combinations are available
  to Paul? Assume that repeating digits in a password is allowed.

Answer: 10^3=1000

- Claudia is organizing her bookshelves. She has 18 books and four shelves. How many
  ways are there to put books on the shelves, if it is possible to leave some
  shelves empty?

Answer: k=18, n=4
C(18+4-1,18)=(18+4-1)!/(4-1)!*18!=21!/3!*18!=21*20*19/3*2*1=7*10*19=1330 ways

- There are 10 residential floors in the building. On the ground floor, 7 people
  get into an elevator and go up. Count the number of ways people can be distributed
  among the floors. There is no need to discriminate between people, only the
  number of people is important.

Answer: K=7, n=10
C(7+10-1,7)=(7+10-1)!/(10-1)!*7!=16!/9!*7!=11440 ways

- Emma wants to buy sunglasses. In the optic shop, she has two options: to buy
  ready-made sunglasses or to build her own sunglasses by combining a frame and
  lenses. To create her own model, Emma has a choice of three frames and two brands
  of lenses, each of which offers two lens options. As for ready-made sunglasses,
  there are six available models. How many options does Emma have if she wants to
  buy sunglasses?

Answer: 6+3*2*2=18

- Jack is having a party. He prepared a lottery with four different prizes for
  his 14 guests. In how many ways can prizes be distributed among the guests if
  each guest can get at most one prize?

Answer: P(14,4)=14*13*12*11=24024

- A team leader has 17 tickets with upcoming deadlines. He has seven developers
  at his disposal. In how many ways can the team leader assign tickets to developers
  if each developer must get at least one ticket to avoid being out of work? There
  is no need to discriminate between tickets, only the number of tickets is important.

Answer: 8008 C(16,6)=P(16,6)/6!=8008, we take away for 1 position from tickets
and devepopers














