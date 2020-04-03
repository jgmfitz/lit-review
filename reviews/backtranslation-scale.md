## Understanding Back-Translation at Scale

Sergey Edunov, Myle Ott, Michael Auli, David Grangier

FAIR, Google Brain

2018

[Link](https://arxiv.org/abs/1808.09381)

### Overview

Parallel corpora (data from one language aligned to another language) are often in short supply. Back-translation is a technique in which an intermediary model is used to first translate monolingual data from the target language into the source language. The final model then uses the back-translated data as an additional dataset for training. In this work, the researchers back-translate hundreds of millions of sentences to achieve state of the art performance on English to German machine translation using the WMT ‘14 benchmark. They used bitext from WMT ‘14 only, as well as 226M additional monolingual sentences.

### Key Findings

1. Sampling from the model distribution or noising beam outputs outperforms pure beam search (the previous standard).
2. 