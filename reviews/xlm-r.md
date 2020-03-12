## Unsupervised Cross-lingual Representation Learning at Scale (the XLM-R paper)

Alexis Conneau, Kartikay Khandelwal, Naman Goyal, Vishrav Chaudhary, Guillaume Wenzek, Francisco Guzmán, Edouard Grave, Myle Ott, Luke Zettlemoyer, Veselin Stoyanov

Facebook

[https://arxiv.org/abs/1911.02116]

### Overview
This is the paper tied to the release of the the Cross Lingual Language Model RoBERTa (XLM-R). The main points are as follows:
* **More data:** They increased data by 100x (for certain languages) versus previous similar work, arguing the mBERT and XLM were undertuned, similar to the claim made for RoBERTa in the monolingual space. Rather than using wikipedia, as in previous work, they used a cleaned CommonCrawls dataset. It also helped to increase the batch size and training time.
* **The curse of multilinguality:** For high resource languages, there is a steady decline in performance (71.8% to 67.7% for XNLI) from 7 to 100 languages. For low resource languages, though, performance actually improves up to 15 languages and then degrades.
* **Bigger is better:** Despite the aforementioned “curse,” a bigger model can overcome many of the accuracy problems. For example, a 30-language model with more parameters can attain parity with a smaller model of 7 languages. A larger vocabulary also helps, as they showed on the older XLM-100 model.
* **Results:** Their model outperforms mBERT by up to 21% for low resource languages, by 3.9% on average for XLNI, by 2.1% on NER, and by 8.4% on Q&A.

### Methods:
They:
* Train using the masked language model objective, with each sample being monolingual.
* Use Sentence Piece for tokenization and formatting of input, which can be used across all languages (versus language-specific implementations used in mBERT and XLM). They did not see any degradation by using Sentence Piece.
* Use a vocabulary of 250k and train two models, XLM-RBase (L= 12, H = 768, A = 12, 270M params) and XLM-R (L = 24, H = 1024, A = 16, 550M params).
* Train on 100 languages across 1.5 Million updates on five hundred 32GB Nvidia V100 GPUs with a batch size of 8192 (!).
* Evaluate on cross-lingual NLI, NER, and QA.

