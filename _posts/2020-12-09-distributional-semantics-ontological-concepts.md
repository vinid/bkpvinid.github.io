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

## Distributional Semantics

Distributional Semantics, is a well-known theory about meaning: the general assumption is that the meaning of a 
word in a sentence can be inferred by looking at the context. Consider the following sentence "The swelybot is very 
friendly and it can be domesticated". Even if you do not know what is the meaning of "swelybot" is, 
you can more or less get a general idea of what "swelybot" might refer to: an animal that can be domesticated.

## Distributional Semantics in the Vector Space

The only way for us to use distributional semantics in computer science/computational linguistics is to brings words and 
sentences to the vector space.

## Distributional Semantics Yesterday and Today

Skipping many years in time, distributional semantic neural network become absurdly popular with the release of the
word2vec paper by Mikolov et al., 2013.

Word2vec trains a one hidden layer neural network[^1]

## Distributional Semantics for Ontological Concepts

A concept we need to introduce to better understand what are we going to talk about is the concept of Knowledge Graph. A knowledge graph is a way to model knoweldge using a graph. Roughly speaking, in a knowledge graph, nodes describe real world entities (e.g., Barack Obama) and edges are relationships that connect the entities (e.g., Barack Obama, born in, Hawaii).

We can use a simple trick to create distributional representations of ontological concepts. We now make two assumptions: we have some text available and we can identify entites of a Knowledge Graph in the text.

## To Know More

Word2vec is now considered an "ond" algorithm (even if it sill has a lot of applications). More recent language models
such as ELMo and BERT tend to be used.

[^1]: This is true for the version of word2vec without negative sampling, that is slightly different.
