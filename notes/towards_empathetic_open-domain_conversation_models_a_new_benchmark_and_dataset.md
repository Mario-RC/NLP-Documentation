
## [Towards Empathetic Open-domain Conversation Models: a New Benchmark and Dataset](https://arxiv.org/abs/1811.00207)

###### TLDR;



#### Key Points

- Most recent powerful language architectures are trained on vast amounts of barely curated text scrapes, social media conversations, or independent books.

- One challenge for dialogue agents is recognizing feelings in the conversation partner and replying accordingly, a key communicative skill.

- Dataset of 25k conversations grounded in emotional situations.

- Dialogue models that use our dataset are perceived to be more empathetic by human evaluators,

- So it is reasonable to expect that dialogue agents would also benefit from empathetic responding.


#### Notes

Through a general term to encourage higher levels of affect [(Asghar et al., 2018)](/notes/affective_neural_response_generation.md), with evaluations focused on matching a predetermined desired emotion rather than empathetic responding. [Niu and Bansal (2018)](/notes/polite_dialogue_generation_without_parallel_data.md) generate responses conditioned on a specified politeness setting (polite, rude or neutral).

Another interesting resource is the DAILYDIALOG (DD) dataset [(Li et al., 2017)](/notes/polite_dialogue_generation_without_parallel_data.md), which comprises about 13k dialogues obtained by crawling educational websites intended for learners of English and also has emotion label annotations. Many of the dialogues are focused on topics for ESL learners (ordering from a restaurant, asking for directions, introductions, etc), but only ≈ 5% of the utterances have a label other than “none” or “happy”.

We used the Hugging Face PyTorch implementation of BERT at https://github.com/huggingface/pytorchtransformers. We experimented with directly fine-tuning BERT on ED without first training on Reddit conversations, but this did not perform as well.


## Results



## Conclusions


