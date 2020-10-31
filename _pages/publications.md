---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---


## ACL 2020

Our recent paper at ACL where we show that using commercial translation systems makes you sound more male and older.

**Paper**: [https://www.aclweb.org/anthology/2020.acl-main.154.pdf](https://www.aclweb.org/anthology/2020.acl-main.154.pdf)

**Press Release**: [https://www.knowledge.unibocconi.eu/notizia.php?idArt=21787](https://www.knowledge.unibocconi.eu/notizia.php?idArt=21787)

Hovy, D., **Bianchi, F.**, & Fornaciari, T. (2020, July). “You Sound Just Like Your Father” Commercial Machine Translation Systems Include Stylistic Biases. In Proceedings of the 58th Annual Meeting of the Association for Computational Linguistics (pp. 1686-1690).

## NPJQI 2020

In our NPJQI paper we show how to implement a deep neural network to reconstruct quantum properties of optical systems.

**Paper:** [https://www.nature.com/articles/s41534-020-0248-6](https://www.nature.com/articles/s41534-020-0248-6)

**Pres Release**: [https://phys.org/news/2020-02-machine-quantum-optics.html](https://phys.org/news/2020-02-machine-quantum-optics.html)

Palmieri, A. M., Kovlakov, E., **Bianchi, F.**, Yudin, D., Straupe, S., Biamonte, J. D., & Kulik, S. (2020). 
Experimental neural network enhanced quantum tomography. npj Quantum Information, 6(1), 1-5.

## RecSys 2020

In our RecSys paper we show how can tackle the cold start problem for product embeddings in the e-commerce using s recent language models such as BERT.

**Paper**: [https://dl.acm.org/doi/10.1145/3383313.3411477](https://dl.acm.org/doi/10.1145/3383313.3411477)

**Pres Release**: [https://blog.coveo.com/solving-the-cold-start-problem/](https://blog.coveo.com/solving-the-cold-start-problem/)

Tagliabue, J., Yu, B., & **Bianchi, F.** (2020, September). The Embeddings That Came in From the Cold: Improving Vectors for New and Rare Products with Content-Based Inference. In Fourteenth ACM Conference on Recommender Systems (pp. 577-578).

## AAAI 2019

In our AAAI paper we show a tool to align distributional vector spaces that can be used to study diachronic change.

**Paper**: [https://www.aaai.org/ojs/index.php/AAAI/article/view/4594](https://www.aaai.org/ojs/index.php/AAAI/article/view/4594)

**Blog Post**: [https://medium.com/@fb_vinid/aligning-temporal-diachronic-word-embeddings-with-a-compass-732ab7427955](https://medium.com/@fb_vinid/aligning-temporal-diachronic-word-embeddings-with-a-compass-732ab7427955)

Di Carlo, V., **Bianchi, F.**, & Palmonari, M. (2019, July). Training temporal word embeddings with a compass. 
In Proceedings of the AAAI Conference on Artificial Intelligence (Vol. 33, pp. 6326-6334).


You can find my other articles on <u><a href="https://scholar.google.com/citations?user=1okGjb8AAAAJ&hl=it">my Google Scholar profile</a>.

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
