---
permalink: /2021-02-14-contextualized-topic-models-1-82-released
title: "Contextualized Topic Models 1.82 Released"
excerpt: "A new version of the contextualized topic model package"
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

We have released a new version of the [contextualized topic modeling](https://github.com/MilaNLProc/contextualized-topic-models) package! As for now, it has been downloaded
18K times! The paper on the cross-lingual model has been accepted at [EACL](https://arxiv.org/pdf/2004.07737v2.pdf)!
We also have been recently featured in the [SIGTYP](https://sigtyp.github.io/sigtyp-newsletter-Feb-2021.html) newsletter, where
we summarize the contribution of our work.

We have worked on the general API in version 1.8, making it easier for other people to use
their own data sets. Moreover, we removed a bottleneck in the predictions of the ZeroShotTM model, making the model faster.

At the same time, we have greatly extended the 
documentation and prepared a [Medium Blog Post](https://fbvinid.medium.com/contextualized-topic-modeling-with-python-eacl2021-eacf6dfa576)
to provide a more general introduction to the ZeroShotTM model.

![https://pepy.tech/badge/contextualized-topic-models](https://pepy.tech/badge/contextualized-topic-models)
[![GitHub stars](https://img.shields.io/github/stars/MilaNLProc/contextualized-topic-models?style=social&label=Star&maxAge=2592000)](https://GitHub.com/MilaNLProc/contextualized-topic-models/stargazers/)
![https://pypi.python.org/pypi/contextualized_topic_models](https://img.shields.io/pypi/v/contextualized_topic_models.svg)
![https://colab.research.google.com/drive/1V0tkpJL1yhiHZUJ_vwQRu6I7_svjw1wb?usp=sharing](https://colab.research.google.com/assets/colab-badge.svg)







