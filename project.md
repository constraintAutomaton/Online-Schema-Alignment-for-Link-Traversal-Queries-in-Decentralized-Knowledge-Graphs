# What do we want
We want lightweight reasoning to do schema alignment while doing traversal queries.
We also want to be able to start with reasoning rules and to append to discover them while traversing.

## What are research questions/Challenges
- How can we do LTQP in practice while doing reasoning
- How can we discover rules and parse them
- Does this reasoning affect speed? Also compared to a SPARQL solution when possible
- Do we modify the results to be in line with the query from the user or do we send the results as is without consideration to the query
### Possible extension
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
- What can we change
    - use a schema.org vocab for profile
    - use a version where the name is in one field
    - Use IRI for gender
    - Use IRI for language
    - Likes with variations

## Approaches with N3

N3 support reasoning "N3.js currently only supports rules with Basic Graph Patterns in the premise and conclusion. Built-ins and backward-chaining are not supported. For an RDF/JS reasoner that supports all Notation3 reasoning features, see eye-js" we might not be able to split a name in two or something like that. But for simple schema alignment it should work. We can also implement the entailment.

- Incremental maintenance
- What is missing, we can add some builtin?





https://aws.amazon.com/blogs/database/build-and-deploy-knowledge-graphs-faster-with-rdf-and-opencypher/ contains another query of which they say "This is considered path discovery and isn’t possible with a single SPARQL query." and is no problem to run in eye  https://github.com/eyereasoner/eye/tree/master/reasoning/path-discovery
