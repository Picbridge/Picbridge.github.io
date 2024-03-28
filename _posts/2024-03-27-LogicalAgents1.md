---
layout: post
tag: AI
---

## [AI] Logical Agents - 1
---
### What is Knowledge Base
![image](https://github.com/Picbridge/Picbridge.github.io/assets/34910988/637e8c6f-c8de-42a6-9525-4bb1bf42145f)

Knowledge Bases is a set of sentences in a formal language. (Collection of statements)

It is known facts.

e.g., 

-   _KB =_ { **A ⇒ B, A** }  -> can always substitute , with ∧ since they are both true. 

indicating that given the truth A implies B and given A is true, Ask if B is true

Ask(B) ? hopefully yes. We hope that our system will be able to do that.  (Modus ponens)

-   _KB =_ { **A ⇒ B, ￢ B** }

Ask( ￢A) ? hopefully yes.  (Modus tollens)

-   _KB_ \= { **A ⇒B, B** }

Ask(A) ? hopefully no -> common error.

**B** maybe implied by something else. (**B** may be true without **A** being true)

#### What is in the knowledge base?

-   Things that you observed (e.g., **A ⇒ B**..)
-   Rules of the world (known to be true)

#### Example: Wumpus World PEAS description

![image](https://github.com/Picbridge/Picbridge.github.io/assets/34910988/52549847-6fc7-475c-a51b-1aed579a0094)

Player starts at position (1, 1), and the goal is to find the gold in the map. Player only has a local percept, and tries to navigate to maximize the score. Player can sense the presence of Wumpus if they are the in one of its four neighboring cells (Von Neumann neighborhood). Similarly, pits produces breeze on its four neighbors, and gold produces glitter only in the cell where it is located. _e.g._, if the agent goes up, it will know that there is a stench.

**Characteristics of the Wumpus world**

-   Not observable (local perception)
-   Deterministic (outcomes exactly specified)
-   Not episodic (sequence of action)
-   Static (Wumpus and pits do not move)
-   Discrete

**Example process steps**
![image](https://github.com/Picbridge/Picbridge.github.io/assets/34910988/09c2fd54-0764-43ac-afa4-c7b4a448ac39)

**Example of tight spots:**

-   Breeze in (2, 1) and (1, 2) ⇒ no safe actions

       5 possible cases = { 3 pits, { (3, 1), (1, 3) },  { (3, 1), (2, 2) }, { (2, 2), (1, 3) }, { (2, 2) }}

       In order to use the probability theory meaningfully, we need to have information about distribution.

      e.g., Given information pits are uniformly distributed, (2, 2) has pit with prob. 0.86

      There is no deterministically safe way to proceed.

#### Entailment

Entailment means that one thing follows from another:

_KB_ |=α

If knowledge base is true, then α is true.

Knowledge base _KB_ entails sentence α if and only if α is true in all worlds where _KB_ is true

e.g., the KB containing "the Giants won" and "the Twins won" entails "Either Giants won or the Twins won" 

Entailment is a relationship between sentences (i.e., syntax) that is based on semantics.

One way of thinking about entailment is by drawing all possible models of the _KB,_ and then observing that for all models when _KB_ is true, α is also true because α includes the models of the knowledge base.

\*Simply speaking, Entailment is a very strong belief of being true, but can't prove it. It's just because. 

#### Models

Possible ways of assigning variables that agrees with observations.

From the tight spot example above:

| 1,3 |   |   |
| --- | --- | --- |
| B | 2,2 |   |
|   | B | 3,1 |

Models:

1) P(1,3) ∧ P(2,2) ∧ P(3,1)

2) P(1,3) ∧ P(2,2)

3) P(1,3) ∧ P(3,1)

4) P(2,2) ∧ P(3,1)

5) P(2,2)

Logicians typically think in terms of models, which are formally structured worlds with respect to which truth can be evaluated.

![image](https://github.com/Picbridge/Picbridge.github.io/assets/34910988/f99bb35b-2752-4d38-a20d-d0fc8a226d99)

We say _m_ is a model of a sentence α if α is true in _m._

M(α) is the set of all models of α.

Then _KB_|= α if and only if M(_KB_) ⊆ M(α)

e.g., _KB_ : Giants won and Twins won

          α :  Giants won

**More example** : 

_KB_ = { **A** **⇒B, A** }   α = **B**

_KB_|= α ?

**\*A** **⇒B** can also be defined****￢A∨B****

If ********A********  is false, ****￢A**** is true, so **B** can be anything. When **A** is true, ****￢A**** is false so **B** better be true.

Result doesn't matter if the assumption is false.

Models : 

| **A** | **B** | ￢A∨B    | **A** | _KB_ | α = {**B**} |
| --- | --- | --- | --- | --- | --- |
| 0 | 0 | 1 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 | 0 |
| 1 | 1 | 1 | 1 | 1 | 1 |

M(_KB_) = { (1, 1, 1, 1, 1, 1 ) }, 

M(α) = { (0, 1, 1, 0, 0, 1), (1, 1, 1, 1, 1, 1) }

Whenever _KB_ is true, α is guaranteed to be true.

**Back to the Wumpus world**,

![image](https://github.com/Picbridge/Picbridge.github.io/assets/34910988/d91072f6-dbf9-4416-aee6-95cb442dc7fb)

These are all possible cases for pit position.

![image](https://github.com/Picbridge/Picbridge.github.io/assets/34910988/3faef14b-8338-4f30-b582-6d14a56295e3)

_KB_ = Wumpus world rules + observations 
​
α1 = "P(1,2) is safe", _KB_|= α1, proved by model checking.
