## Cross-Lingual Ability of Multilingual BERT: An Empirical Study

K, Wang, et al.

IIT Kanpur, U Illinois, Duolingo, U Penn

2020 - ICLR

[Link](https://arxiv.org/pdf/1912.07840.pdf)

### Summary

In previous multilingual modeling efforts, in which a single model is used to ingest text from multiple languages, it seemed that languages that are more similar would work better together (EX: the Romance languages). This study shows that lexical overlap is a negligible factor in cross-lingual modeling performance. Instead, model depth and parameter count matter most (at least for entailment and for named entity recognition).

### Methods and Results

#### Word Piece Overlap

Word piece overlap is gauged by creating a "Fake English," wherein the unicode had been shifted by a large constant for the entire English vocabulary. 
