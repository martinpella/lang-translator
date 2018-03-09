# lang-translator
In this project a sequence to sequence model is trained to build a French - English translator.

### Dataset
French-English 10<sup>9</sup> corpus from <a href="http://www.statmt.org/wmt10/translation-task.html">ACL 2010 FIFTH WORKSHOP ON STATISTICAL MACHINE TRANSLATION</a> is used. It was crawled from Canadian and European Union sources. Since the scope of the project is limited to translate questions, the definition of the correct corpus subset is carried out as preprocessing step.

### Pre-trained word embeddings
Words are represented by numerical vectors. Given that the used corpus subset contains roughly 52000 questions, we leverage on pre-trained vectors (there is no enough data to train them from scratch).
<br/>English: the 100-dimensional <a href="https://nlp.stanford.edu/projects/glove/">GloVe</a> embeddings of 400k words computed on a 2014 dump of English Wikipedia.
<br/>French: the 200-dimensional <a href="http://fauconnier.github.io/">frWac2Vec</a> embeddings computed using Word2vec skip-gram approach on a 1.6 billion word corpus constructed from the Web limiting the crawl to the .fr domain.

### Sequence-to-sequence learning
Encoder and decoder are built using Recurrent Neural Networks in order to create a seq2seq prediction model for machine translation. Then training, inference and evaluation functions are coded. PyTorch is the deep-learning framework used.
