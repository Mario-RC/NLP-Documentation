
## [Towards Empathetic Open-domain Conversation Models: a New Benchmark and Dataset](https://arxiv.org/abs/1811.00207)

#### Key Points

- This work aims to facilitate evaluating models’ ability to produce empathetic responses. A new task for dialogue systems to respond to people discussing situations that cover a wide range of emotions, and EMPATHETICDIALOGUES (ED). Each dialogue is grounded in a specific situation where a speaker was feeling a given emotion, with a listener responding.

- Most recent powerful language architectures are trained on vast amounts of barely curated text scrapes, social media conversations, or independent books.

- One challenge for dialogue agents is recognizing feelings in the conversation partner and replying accordingly, a key communicative skill.

- Dataset of 25k conversations grounded in emotional situations, gathered from 810 different participants [(direct download)](https://github.com/facebookresearch/EmpatheticDialogues).

- Dialogue models that use our dataset are perceived to be more empathetic by human evaluators, so it is reasonable to expect that dialogue agents would also benefit from empathetic responding.

- Prepending Top-k Predicted Labels This setup (Fig. 5), PREPEND-1, is a very simple way to add supervised information to data, requires no architecture modification, and can be used with black-box classifiers.

  - **Original**: “I finally got promoted!”
  - **Prepend-1**: “proud I finally got promoted!”

#### Notes

Through a general term to encourage higher levels of affect [(Asghar et al., 2018)](/notes/affective_neural_response_generation.md), with evaluations focused on matching a predetermined desired emotion rather than empathetic responding. [Niu and Bansal (2018)](/notes/polite_dialogue_generation_without_parallel_data.md) generate responses conditioned on a specified politeness setting (polite, rude or neutral).

Another interesting resource is the DAILYDIALOG (DD) dataset [(Li et al., 2017)](/notes/dailydialog_a_manually_labelled_multi-turn_dialogue_dataset.md), which comprises about 13k dialogues obtained by crawling educational websites intended for learners of English and also has emotion label annotations. Many of the dialogues are focused on topics for ESL learners (ordering from a restaurant, asking for directions, introductions, etc), but only ≈ 5% of the utterances have a label other than “none” or “happy”.

We used the Hugging Face PyTorch implementation of BERT at https://github.com/huggingface/pytorchtransformers. We experimented with directly fine-tuning BERT on ED without first training on Reddit conversations, but this did not perform as well.

We consider an open-domain one-on-one conversational setting where two people are discussing a situation that happened to one of them, related to a given feeling. Emotional situation grounding Each conversation is grounded in a situation, which one participant writes about in association with a given emotion label. These emotion labels cover a broad range of positive and negative emotions. We consider 32 emotion labels, listed in Figure 3:

![Emotions Table](/images/emotions_table.png)

_Figure 3: Distribution of conversation labels within EMPATHETICDIALOGUES training set and top 3 content words used by speaker/listener per category._

The person who wrote the situation description (Speaker) initiates a conversation to talk about it. The other conversation participant (Listener) becomes aware of the underlying situation through what the Speaker says and responds. Speaker and Listener then exchange up to 6 more turns.
