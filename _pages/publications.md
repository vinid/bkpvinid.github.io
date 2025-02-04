---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

You can find most of my work on my [Google Scholar](https://scholar.google.com/citations?user=1okGjb8AAAAJ&hl=it) profile.
Here's some recent stuff I have been doing:

### Cross-lingual Contextualized Topic Models with Zero-shot Learning

In our EACL2021 paper, we introduce a novel variational topic model that combines the expressive powers of contextual embeddings (such as BERT) with
the capabilities of topic models. We get ZeroShotTM a model that can predict topics for unseen languages!

Bianchi, F., Terragni, S., Hovy, D., Nozza, D., & Fersini, E. (2021).  Cross-lingual Contextualized Topic Models with Zero-shot Learning. EACL. https://arxiv.org/pdf/2004.07737v1.pdf

+ **Paper**: [https://arxiv.org/abs/2004.07737](https://arxiv.org/abs/2004.07737)
+ **Python Package**: [https://github.com/MilaNLProc/contextualized-topic-models](https://github.com/MilaNLProc/contextualized-topic-models)

### BERT Goes Shopping

Our recent paper on how to use BERT for eCommerce Products, introducing ProdBERT! We show that ProdBERT is very good for next event prediction, but
that it also requires a very big amount of training data to work efficiently.

+ **Paper**: [https://arxiv.org/abs/2012.09807](https://arxiv.org/abs/2012.09807)

### Knowledge Graphs for eXplainable AI 

Our recent chapter was published in the Knowledge Graphs for eXplainable AI book. We explore the state of the art of knowledge graph embeddings and describe
possible applications for explainability in artificial intelligence 

+ **Paper**: [https://arxiv.org/abs/2004.14843](https://arxiv.org/abs/2004.14843)

**Bianchi, F.**, Rossiello, G., Costabello, L., Palmonari, M., & Minervini, P. (2020). Knowledge Graph Embeddings and Explainable AI. arXiv preprint arXiv:2004.14843.

### ACL 2020

Our recent paper at ACL where we show that using commercial translation systems makes you sound more male and older.

+ **Paper**: [https://www.aclweb.org/anthology/2020.acl-main.154.pdf](https://www.aclweb.org/anthology/2020.acl-main.154.pdf)
+ **Press Release**: [https://www.knowledge.unibocconi.eu/notizia.php?idArt=21787](https://www.knowledge.unibocconi.eu/notizia.php?idArt=21787)

Hovy, D., **Bianchi, F.**, & Fornaciari, T. (2020, July). “You Sound Just Like Your Father” Commercial Machine Translation Systems Include Stylistic Biases. In Proceedings of the 58th Annual Meeting of the Association for Computational Linguistics (pp. 1686-1690).

### NPJQI 2020

In our NPJQI paper we show how to implement a deep neural network to reconstruct quantum properties of optical systems.

+ **Paper:** [https://www.nature.com/articles/s41534-020-0248-6](https://www.nature.com/articles/s41534-020-0248-6)
+ **Pres Release**: [https://phys.org/news/2020-02-machine-quantum-optics.html](https://phys.org/news/2020-02-machine-quantum-optics.html)

Palmieri, A. M., Kovlakov, E., **Bianchi, F.**, Yudin, D., Straupe, S., Biamonte, J. D., & Kulik, S. (2020). 
Experimental neural network enhanced quantum tomography. npj Quantum Information, 6(1), 1-5.

### RecSys 2020

In our RecSys paper we show how can tackle the cold start problem for product embeddings in the e-commerce using s recent language models such as BERT.

+ **Paper**: [https://dl.acm.org/doi/10.1145/3383313.3411477](https://dl.acm.org/doi/10.1145/3383313.3411477)
+ **Pres Release**: [https://blog.coveo.com/solving-the-cold-start-problem/](https://blog.coveo.com/solving-the-cold-start-problem/)

Tagliabue, J., Yu, B., & **Bianchi, F.** (2020, September). The Embeddings That Came in From the Cold: Improving Vectors for New and Rare Products with Content-Based Inference. In Fourteenth ACM Conference on Recommender Systems (pp. 577-578).

### AAAI 2019

In our AAAI paper we show a tool to align distributional vector spaces that can be used to study diachronic change.

+ **Paper**: [https://www.aaai.org/ojs/index.php/AAAI/article/view/4594](https://www.aaai.org/ojs/index.php/AAAI/article/view/4594)
+ **Blog Post**: [https://medium.com/@fb_vinid/aligning-temporal-diachronic-word-embeddings-with-a-compass-732ab7427955](https://medium.com/@fb_vinid/aligning-temporal-diachronic-word-embeddings-with-a-compass-732ab7427955)

Di Carlo, V., **Bianchi, F.**, & Palmonari, M. (2019, July). Training temporal word embeddings with a compass. 
In Proceedings of the AAAI Conference on Artificial Intelligence (Vol. 33, pp. 6326-6334).



{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
