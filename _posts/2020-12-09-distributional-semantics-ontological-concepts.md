---
permalink: /2020-12-09-distributional-semantics-ontological-concepts
title: "Distributional Semantics for Ontological Concepts"
excerpt: "Distributional Semantics has been often applied to represent words and sometimes entities, but it
can also be used to represent ontological concepts"
author_profile: true


defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: true
      share: true
      related: true
---

(In Progress)
The main idea behind this blog post is to give an overview of some of the work I did on combining distributional semantics methods with
ontological representation learning.

## Ontological Concepts

Ontological concepts are used to categorize entities. For example, the concept that categorize Barack Obama and Donald Trump, might be **Politician**. Concepts are also referred to as types.
Types are also often organized in hierarchies, indicating subclass of relationships: for example, the type Politician is subclass of the type **Person**.

The following image shows an ontology[^3] with some entities (often referred to as instances). **Barack Obama**, **Italy** and **Tiber** are entities (yellow circles), while the others are Types (**Thing** is a special super type in this case). We can see that the types are organized in a hierarchy. The dotted lines represent a subclass of relationships, meaning, for example, that a Politician is also a Person. Normal lines instead represent an **instance of** predicate, meaning that **Barack Obama** is a **Politician** (but also a **Person**, and a **Thing**).

![](https://github.com/vinid/vinid.github.io/raw/f316aaad1119e9257f833f3587706a27d1857f5f/images/posts/ds/blog_ontology_hierarchy.png)

### Similarity

One important task is to define how similar are two different ontological concepts. In the literature this has often been done with distance measures over the hierarchy. There are many different measures that can be considered,[^2] but they share all the same basic idea of distance.

## Distributional Semantics

Distributional Semantics, is a well-known theory about meaning: the general assumption is that the meaning of a 
word in a sentence can be inferred by looking at the context. Consider the following sentence "The swelybot is very 
friendly and it can be domesticated". Even if you do not know what is the meaning of "swelybot" is, 
you can more or less get a general idea of what "swelybot" might refer to: an animal that can be domesticated.

## Distributional Semantics in The Vector Space
During the various years that followed the introduction of distributional semantics, people started to introduce different methods to incorprare distributional semantics into language. 

The only way for us to use distributional semantics in computer science/computational linguistics is to brings words and 
sentences to the vector space.

Skipping many years in time, distributional semantic neural network become absurdly popular with the release of the
word2vec paper by Mikolov et al., 2013.

Word2vec trains a one hidden layer neural network[^1] end essentially it learns to predict a word from a neighbouring word and viceversa. During this training process, it learns the representation of words. These representations, based on the co-occurrence of the word in a corpus, can be used for many different tasks. More importantly, since the model is inspired by distributional semantics, these representations exibit some expected qualities, for example, similar words will have similar vectors.

The following image sums everything up:
![](https://github.com/vinid/vinid.github.io/raw/3b90046e970d8347dc9afc4a1870e79a26639f81/images/posts/ds/blog_distributional_semantics_id.png)
The most simplistic way to see distributional semantics when applied in computation is to think of it has a method to put words that appear in similar contexts into close positions in a vector space.

## Distributional Semantics for Ontological Concepts

A concept we need to introduce to better understand what are we going to talk about is the concept of Knowledge Graph. A knowledge graph is a way to model knoweldge using a graph. Roughly speaking, in a knowledge graph, nodes describe real world entities (e.g., Barack Obama) and edges are relationships that connect the entities (e.g., Barack Obama, born in, Hawaii).

We can use a simple trick to create distributional representations of ontological concepts. We now make two assumptions: we have some text available and we can identify entites of a Knowledge Graph in the text.
The following figure shows the process with simple and high level steps. 
![](https://github.com/vinid/vinid.github.io/raw/master/images/posts/ds/ds_process_types.jpg)

The key difference between this representation and the other standard metric used for similarity evaluation is that this kind of representation allow us to evaluate a usage-based similarity between concepts. We can see some examples in the next table.

| Type 1           | Type 2                  | Sim - wpath | Sim - T2V |
|------------------|-------------------------|-------------|-----------|
| dbo:SoccerPlayer | dbo:SoccerClub          | 0.17        | 0.72      |
| dbo:SoccerPlayer | dbo:Wrestler            | 0.47        | 0.24      |
| dbo:RailwayLine  | dbo:Station             | 0.44        | 0.81      |
| dbo:Vein         | dbo:Artery              | 0.70        | 0.84      |
| dbo:RailwayLine  | dbo:PublicTransitSystem | 0.11        | 0.79      |
| dbo:Company      | dbo:Airline             | 0.72        | 0.30      |


What is clear, is that the T2V similarity gives a different interperetation to the concept of similar ty: SoccerPlayer and SoccerClub are similar because they co-occur in similar contexts; however, a Company and an Airline are indeed related but not very similar has they might occur in different contexts.


## To Know More
You can find the main ideas that drove this blogpost in the two following works:

+ Bianchi, F., Palmonari, M., & Nozza, D. (2018, October). Towards encoding time in text-based entity embeddings. In International Semantic Web Conference (pp. 56-71). Springer, Cham.
+ Bianchi, F., Soto, M., Palmonari, M., & Cutrona, V. (2018). Type Vector Representations from Text: An Empirical Analysis. In DL4KGS@ ESWC (pp. 72-83).


Word2vec is now considered an "ond" algorithm (even if it sill has a lot of applications). More recent language models
such as ELMo and BERT tend to be used.

[^1]: This is true for the version of word2vec without negative sampling, that is slightly different.
[^2]: See **Zhu, G., & Iglesias, C. A. (2016). Computing semantic similarity of concepts in knowledge graphs. IEEE Transactions on Knowledge and Data Engineering, 29(1), 72-85.** for an interesting discussion over different measures.
[^3]: This ontology is strongly inspired by the DBpedia Ontology.