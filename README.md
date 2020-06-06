# neo4j-academia
A neo4j implementation of an academic publication model

This work is based on a project on the Semantic Data Management course I followed in Barcelona in the summer semester 2018-2019 as part of the [BDMA](https://bdma.ulb.ac.be/bdma/) Erasmus Mundus Master program.

It was done in collaboration with my lab mate [Elena Ouro](https://github.com/elenaouro).

![graph_model](/static/graph_extended.png)

We designed and implemented a graph like the figure above. We prepared and loaded a combination of real and synthetic data (see [notebooks](/notebooks)). We also run some Cypher queries on the database (calculate h-index, journal impact factor, etc) and built a simple recommender system based on pagerank for recommending reviewers for articles of the database community (see [scripts](/scripts)).

Check my [blog post](http://localhost:1313/posts/neo4j-recommender) for more details.
