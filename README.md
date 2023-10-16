# The Dad-Joke Generator
Information Extraction system done as a final project for my Information Extraction class. It turned out quite funny.


# The idea behind the project

Since this is my first complex NLP project, I decided to keep it light & funny (a method to cope with coding-induced frustrations) and work with (really bad) dad-jokes. The idea behind it was creating an information extraction system that indexes dad-jokes and returns jokes containing a certain keyword prompted by the user, therefore acting as a "dad-joke generator". (Note to self: create an actual joke generator next time)

### The Data
The dataset I ended up working with consisted of two existing datasets I found on Kaggle: 
  
* the Reddit Dad Jokes dataset: https://www.kaggle.com/datasets/oktayozturk010/reddit-dad-jokes
* and the Short Jokes dataset: https://www.kaggle.com/datasets/abhinavmoudgil95/short-jokes

### The Preprocessing

For the preprocessing step, I created a reusable pipeline class which includes several preprocessing steps such as tokenization, lemmatization, stop-words removal, case-folding, etc.

### Indexing 

For the indexing I trained a Word2vec model & used it to create word embeddings which I saved into a FAISS database.

### The retrieval: querying & ranking

I queried the FAISS database using simple keyword queries & Word2Vec's **most_similar** method for query expansion. I ranked the queries using the **Okapi BM25 ranking function** which calculates the relevance score between the query and a joke based on term frequency, document length, and inverse document frequency.

### The interface

To keep it fun, I decided to create an interface for my system using JupyterDash. 

<img width="1137" alt="image" src="https://github.com/patriciacarla04/The-Dad-Joke-Generator/assets/113781516/109b80c2-3ca3-4bef-9ecf-40c5ff2ef627">


