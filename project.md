# What do we want
We want lightweight reasoning to do schema alignment while doing traversal queries.
We also want to be able to start with reasoning rules and to append to discover them while traversing.

## What are research questions/Challenges
- How can we do LTQP in practice while doing reasoning
- How can we discover rules and parse them
- Can we detect, solve, or manage possible contradictions in the rules
- Do we need some policies to choose which rule to include (can a rule change the traversal)
- Does this reasoning affect speed? Also compared to a SPARQL solution when possible
- Do we modify the results to be in line with the query from the user or do we send the results as is without consideration to the query

## Are we doing scientific research what is the state of the art

What kind of publication are we seeking? What is the scope of the study.
## What is the current approach

### We can do now
- For schema alignment, we can write queries with unions.
- For some reasoning, we can build the query in a way to encompasse it
### Prospective
- There seem to be two schools
    - Rewrite the query
    - Modify the triples in the triple store

## How to evaluate the solutions?
- We can use solidbench and at random change the vocabulary of some terms
    - We use the same queries as we have right now
    - We create versions of those queries that can cope with the alternative