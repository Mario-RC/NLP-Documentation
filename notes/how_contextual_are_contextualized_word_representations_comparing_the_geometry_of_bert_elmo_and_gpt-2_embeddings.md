
## [How Contextual are Contextualized Word Representations? Comparing the Geometry of BERT, ELMo, and GPT-2 Embeddings](https://arxiv.org/abs/1909.00512)

###### Conclusion

In ELMo, BERT, and GPT-2, upper layers produce more context-specific representations than lower layers. However, these models contextualize words very differently from one another: after adjusting for anisotropy, the similarity between words in the same sentence is highest in ELMo but almost non-existent in GPT-2. This suggests that ELMo, BERT, and GPT-2 are not simply assigning one representation per word sense; otherwise, there would not be so much variation in the representations of words with so few word senses.

On average, less than 5% of the variance in a word’s contextualized representations can be explained by a static embedding. Even in the best-case scenario, static word embeddings would thus be a poor replacement for contextualized ones. Still, contextualized representations can be used to create a more powerful type of static embedding: principal components of contextualized representations in lower layers of BERT are much better than GloVe and FastText!