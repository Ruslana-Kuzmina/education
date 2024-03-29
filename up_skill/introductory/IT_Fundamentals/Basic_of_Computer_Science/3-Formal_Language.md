# Formal Languages

## Finite State Machine

A finite-state machine, or FSM for short, is an abstract machine that can be
in exactly one of a finite number of states at any given time. The FSM can
transition from one state to another as a response to some inputs. The change
from one state to another is called a **transition**. The FSM is often represented
as a directed graph.

FSM is defined by:

- the list of its states
- the alphabet which is just a list of all possible input characters
- the initial state
- the list of accepting states
- the list of transitions which can be represented by a two-dimensional table
  (state x character)

In case of syntax checking, the inputs are characters from a string being checked
for correct syntax. The input string is read character by character. Each new
character triggers a transition.
14.5E+5 (14.5×105)

There are two state:

- Deterministic

The next state is uniquely determined by the current state and the next symbol.
The machine accepts a string if it ends up in an accepting state after consuming
all symbols in the string. The example of an FSM accepting numbers in E notation
shown previously is a deterministic FSM.

- Non-Deterministic

The next state is not necessarily uniquely determined by the current state and
the next symbol.The machine can transition to another state without reading any
input symbol. This is usually shown as an ε symbol on a state diagram.
Suppose the machine shown below is in state 1 and the next symbol is "a". It can
transition loop back to state 1 or it can transition to state 2. It also can
transition to state 3 without reading the symbol "a". The machine accepts a
string if there exists a "lucky run" which leads to an accepting state.

## Regular Expressions

We have already shown that FSMs can be used to check if a string matches some
pattern. However, constructing FSMs by hand is quite a complex task and nobody
does that. The regular expressions (often shortened as regex or regexp) is another
way to check if a string matches the pattern. A regular expression is a sequence
of characters that forms a search pattern. It is much easier to write a regex
matching a pattern than to construct a FSM doing the same task.

Regular expressions have many different implementations which slightly vary in
their syntax. However, the basics of syntax are the same.

There is a direct link between regular expressions and FSMs. It can be shown that
any regular expression can be converted to an equivalent non-deterministic FSM
accepting the same set of strings which is matched by this regular expression.
As we mentioned before, a non-deterministic FSM can be converted to a deterministic
FSM. A DFSM is a set of instructions which can be easily performed by a computer.
Every time you use a regular expression in your code or in a text editor, behind
the scenes, it is converted to a DFSM to test if there is a match.
