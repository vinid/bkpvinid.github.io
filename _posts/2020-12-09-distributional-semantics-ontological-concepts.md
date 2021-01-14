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

(In Progress - Draft)
The main idea behind this blog post is to give an overview of some of the work I did on combining distributional semantics methods with
ontological representation learning.

## Introduction

Being able to represent ontological concepts (e.g., **Country**, **City**, **Person**) is important for many tasks in both Natural Language Processing and the Semantic Web. For example, it can be useful in Named Entity Recognition, where we need to be able to distinguish different kinds of elements.

Two key factors of ontologies are that they allow us to organize knowledge and that they also allow us to evaluate how similar two concepts are. Ontologies are generally defined as subclass of hierarchies (**Politician** is a subclass of **Person**) and thus, the similarity between concepts can be defined in terms of distance of the concepts in the hierarchy (e.g., **City** and **Town** are much more similar than **City** and **Mammal**).

However, this view does not account for how concepts are used and referred to in the real world. For example, the concepts **SoccerPlayer** and **SoccerClub** are completely different from a structural point of view, but they sure are related. Applying distributional semantics methods to ontological concepts can give a different point of view on concept similarity evaluation.

## Ontological Concepts 

Ontological concepts are used to categorize entities. For example, the concept that categorizes Barack Obama and Donald Trump might be **Politician**. Note that concepts are also referred to as types.

Types are also often organized in hierarchies, indicating subclass of relationships: for example, the type Politician is subclass of the type **Person**.

A concept we need to introduce to better understand what are we going to talk about is the concept of Knowledge Graph. A knowledge graph is a way to model knowledge using a graph. Roughly speaking, in a knowledge graph, nodes describe real-world entities (e.g., Barack Obama) and edges are relationships that connect the entities (e.g., Barack Obama, born in, Hawaii).

The following image shows an exmample of what is usually called a knowledge graph (I have removed relationships) with an ontology[^3]. The ontology helps in categorizing the entities (often referred to as instances). **Barack Obama**, **Italy** and **Tiber** are entities (yellow circles), while the others are Types (**Thing** is a special super type in this case). We can see that the types are organized in a hierarchy. The dotted lines represent a subclass of relationships, meaning, for example, that a Politician is also a Person. Normal lines instead represent an **instance of** predicate, meaning that **Barack Obama** is a **Politician** (but also a **Person**, and a **Thing**).

![](https://github.com/vinid/vinid.github.io/raw/master/images/posts/ds/blog_ontology_hierarchy.png)

### Similarity

As we said above, one important task is to define how similar two different ontological concepts are. In the literature, this has often been done with distance measures over the hierarchy. There are many different measures that can be considered,[^2] but they share all the same basic idea of distance.

## Language-based Concept Representations

These hierarchies are often artificial and manually defined and the general sense of similarity is given by topological aspects of the hierarchy. For example, in DBpedia, the types SoccerPlayer and SoccerClub are far and thus not similar.

In this blog post, we want to explore a language-based way to represent concepts in such a way that concepts that share linguistic contexts (appear in similar contexts), are deemed to be similar.

### Distributional Semantics

Distributional Semantics, is a well-known theory about meaning: the general assumption is that the meaning of a 
word in a sentence can be inferred by looking at the context. Consider the following sentence "The swelybot is very friendly and can be easily domesticated". Even if you do not know what is the meaning of "swelybot" is, 
you can more or less get a general idea of what "swelybot" might refer to an animal that can be domesticated. To know more about distributional semantics I suggest looking at [this set of slides](https://esslli2016.unibz.it/wp-content/uploads/2015/10/dsm_tutorial_part1.slides.pdf).

### Distributional Semantics in The Vector Space
During the various years that followed the introduction of distributional semantics, people started to introduce different methods to incorporate distributional semantics into language. 

The only way for us to use distributional semantics in computer science/computational linguistics is to bring words and 
sentences to the vector space.

Skipping many years in time, distributional semantic became very popular with the release of the
word2vec paper by Mikolov et al., 2013.

Word2vec trains a one hidden layer neural network[^1] end essentially it learns to predict a word from a neighboring word (or vice versa). During this training process, it learns the representation of words. These representations, based on the co-occurrence of the word in a corpus, can be used for many different tasks. More importantly, since the model is inspired by distributional semantics, these representations exhibit some expected qualities, for example, similar words will have similar vectors.

The following image sums everything up:
![](https://github.com/vinid/vinid.github.io/raw/3b90046e970d8347dc9afc4a1870e79a26639f81/images/posts/ds/blog_distributional_semantics_id.png)
The most simplistic way to see distributional semantics when applied in computation is to think of it as a method to put words that appear in similar contexts into close positions in a vector space.

### Distributional Semantics for Ontological Concepts

We can use a simple trick to create distributional representations of ontological concepts. We now make two assumptions: we have some text available and we can identify entities of a Knowledge Graph in the text. Thus, given in input a text, we first annotate it using an entity linker (e.g., [DBpedia Spotlight](https://www.dbpedia-spotlight.org/demo/), we remove the words and then we replace the entities with their most specific type in the ontology. Thus, we go from text, to entities of a knowledge graph and finally to the types of those entities.

The following figure shows the process with simple and high-level steps. 
![](https://github.com/vinid/vinid.github.io/raw/master/images/posts/ds/ds_process_types.jpg)

Given the text, DBpedia Spotlight allows us to find the entities **Tiber** and **Italy**[^4] in the text, and then we replace them with **River** and **Country**. Then, we apply the word2vec algorithm to generate type representations. We call this approach Type2Vec (T2V).

The key difference between this representation and the other standard metric used for similarity evaluation is that this kind of representation allows us to evaluate a usage-based similarity between concepts. We can see some examples in the next table in which we compare the similarity computed using T2V (cosine similarity) with one of the measures used in the literature to compute the distance between two concepts[^2] (in this case, we are using the wpath).

| Type 1           | Type 2                  | Sim - wpath | Sim - T2V |
|------------------|-------------------------|-------------|-----------|
| dbo:SoccerPlayer | dbo:SoccerClub          | 0.17        | 0.72      |
| dbo:SoccerPlayer | dbo:Wrestler            | 0.47        | 0.24      |
| dbo:RailwayLine  | dbo:Station             | 0.44        | 0.81      |
| dbo:Vein         | dbo:Artery              | 0.70        | 0.84      |
| dbo:RailwayLine  | dbo:PublicTransitSystem | 0.11        | 0.79      |
| dbo:Company      | dbo:Airline             | 0.72        | 0.30      |


What is clear, is that the T2V similarity gives a different interpretation to the concept of similar ty: **SoccerPlayer** and **SoccerClub** are similar because they co-occur in similar contexts; instead, the wpath measure, that is based on distance, tells us that **SoccerPlayer** and **SoccerClub** are not similar, because they are very far in the ontology. On the other hand, a **Company** and an **Airline** are indeed related but not very similar as they might occur in different contexts.

Another very interesting example, is shown in the next table. Whereas wpath tells us that **SoccerPlayer**, **BasketballPlayer** and **ChessPlayer** are all equally similar because they share the same parent node (i.e., they are all siblings in the ontology, at the same level). T2V tells us that **SoccerPlayer** is much more similar to **BasketballPayer** than to **ChessPlayer**, giving us a more meaninful result, as Soccer and Basketball are sports that have more in common than Soccer and Chess.

| Type 1           | Type 2                  | Sim - wpath | Sim - T2V |
|------------------|-------------------------|-------------|-----------|
| dbo:SoccerPlayer | dbo:BasketballPlayer    | 0.47        | 0.74      |
| dbo:SoccerPlayer | dbo:ChessPlayer         | 0.47        | 0.44      |


## To Know More
You can find the main ideas that drove this blogpost in the two following works:

+ Bianchi, F., Palmonari, M., & Nozza, D. (2018, October). Towards encoding time in text-based entity embeddings. In International Semantic Web Conference (pp. 56-71). Springer, Cham.
+ Bianchi, F., Soto, M., Palmonari, M., & Cutrona, V. (2018). Type Vector Representations from Text: An Empirical Analysis. In DL4KGS@ ESWC (pp. 72-83).

Word2vec is now considered an "old" algorithm (even if it still has a lot of applications). More recent language models
such as ELMo and BERT tend to be used.

[^1]: This is true for the version of word2vec without negative sampling, which is slightly different.
[^2]: See **Zhu, G., & Iglesias, C. A. (2016). Computing semantic similarity of concepts in knowledge graphs. IEEE Transactions on Knowledge and Data Engineering, 29(1), 72-85.** for an interesting discussion over different measures.
[^3]: This ontology is strongly inspired by the DBpedia Ontology.
[^4]: dbr is a prefix that identifies a DBpedia resource/entity while dbo identifies elements of the ontology.

