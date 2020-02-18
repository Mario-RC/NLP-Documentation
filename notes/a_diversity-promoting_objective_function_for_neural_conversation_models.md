
#### [A Diversity-Promoting Objective Function for Neural Conversation Models](https://arxiv.org/abs/1510.03055)


###### TLDR;

To deal with the issue that SEQ2SEQ models tend to generate generic and commonplace responses such as I don’t know, we follow Li et al. (2016) by reranking the generated N-best list using a scoring function that linearly combines a length
penalty and the log likelihood of the source given the target:

log p(R|M, v) + λ log p(M|R) + γ|R| (11)

where p(R|M, v) denotes the probability of the generated response given the message M and the respondent’s speaker ID. |R| denotes the length of the target and γ denotes the associated penalty weight. We optimize γ and λ on N-best lists of response candidates generated from the development set using MERT (Och, 2003) by optimizing BLEU. To compute p(M|R), we train an inverse SEQ2SEQ model by swapping messages and responses. We trained standard SEQ2SEQ models for p(M|R) with no speaker information considered.

#### Key Points


