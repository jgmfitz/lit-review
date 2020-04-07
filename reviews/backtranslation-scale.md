## Understanding Back-Translation at Scale

Sergey Edunov, Myle Ott, Michael Auli, David Grangier

FAIR, Google Brain

2018

[Link](https://arxiv.org/abs/1808.09381)

### Overview

Parallel corpora (data from one language aligned to another language) are often in short supply. Back-translation is a technique in which an intermediary model is used to first translate monolingual data from the target language into the source language. The final model then uses the back-translated data as an additional dataset for training. In this work, the researchers back-translate hundreds of millions of sentences to achieve state of the art performance on English to German machine translation using the WMT ‘14 benchmark. They used bitext from WMT ‘14 only, as well as 226M additional monolingual sentences.

### Key Findings

1. Sampling from the model distribution or noising beam outputs outperforms pure beam search (the previous standard).
2. Synthetic data based on sampling and noised beam search provides a stronger signal than that based on argmax inference.
3. Back-translated data can sometimes match the accuracy of real bitext.
4. Unlike other methods, back-translation requires no architectural changes to the model.

### Methods

They use a encoder-decoder transformer architecture with 6 blocks in the encoder and in the decoder. Word embeddings are 1,024, drop out is 0.3, and 16 attention heads are used. Adam is the optimizer. Decoding used a beam size of 5. 

After obtaining 5.18M bilanguage pairs and 226M target sentences, they the use Moses for tokenization and byte pair encoding. They use BLEU and de-tokenized BLEU for eval. 















