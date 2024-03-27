## [AI] Constraint Satisfaction Problems - 1
---

# What is Constraint Satisfaction Problems

Set of objects whose state must satisfy a number of constraints or limitations  
Offers a framework for solviong problems that involve finding configurations of variables that meet a specified set of conditions.

## Components

### Variables

A set of variables that need to be assigned values.

### Domains

For each variable, there is a domain of possible values that the variable can take.

### Constraints

Rules that specify which combinations of values are valid

Scope

-   The scope of a constraint refers to the set of variables that the constraint involves or applies to.
-   e.g., You have a constraint that specifies that variable **X** must be less than variable **Y**, then the scope of this constraint is the pair of variables (**X**,**Y**). In essence, the scope outlines which parts of the problem the constraints is concerned with. In binary constraints, the scope involves exactly two variables, while in n-ary constraints, the scope can involve _n_ variables, where _n_ can be any integer greater or equal to 2.

Relation (Rel)

-   The relation of a constraint specifies the allowed combinations of values for the variables within the scope of the constraint. It defines the specific conditions that the variable assignments must meet to satisfy the constraint. Continuing with the previous example, where **X** < **Y**, the relation is that the value assigned to **X** must be less than the value assigned to **Y**. The relation is essentially the rule that determines whether a particular set of variable assignments is valid or not according to the constraint.

![스크린샷 2024-03-25 233618](https://github.com/Picbridge/Picbridge.github.io/assets/34910988/a1f68e86-00e2-4c81-9d6a-cc4b0934a7c8)
![스크린샷 2024-03-26 000117](https://github.com/Picbridge/Picbridge.github.io/assets/34910988/46ac1251-ae9a-492a-84ba-2373f1efbab2)

A typical CSP example is the coloring problem. It is a problem of assigning different values to two adjacent vertices in the graph.  
Assigning value to each variables is a state in CSP.  
e.g., {Xi = vi, Xj = vj, ...}

## Varieties of CSPs

### Discrete Variables

Finite Domains e.g., Boolean CSPs  
Infinite Domains e.g., Job scheduling, variables are start/end days for each job

### Continuous Variables

e.g., start/end times for Hubble telescope observations

## Varieties of Constraints

### Unary constraints

involve a single variable,

e.g., SA != green

### Binary constraints

involve pairs of variables

e.g., SA != WA

### Higher-order constraints

involve 3 or more variables,

e.g., cryptarithmatic column constraints

### Preferences (soft constraints),

e.g., red is better than green  
often representable by cost for each variable assignment -> constrained optimization problems
