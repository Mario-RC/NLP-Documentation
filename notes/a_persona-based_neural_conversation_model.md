
## [A Persona-Based Neural Conversation Model](https://arxiv.org/abs/1603.06155)


#### Key Points

- Dataset, model and trainning
  - Seq2Seq
  - Speaker Model: Twitter FireHouse dataset
  - Speaker-Addressee Model: Television Series Transcripts (American television comedies Friends and The Big Bang Theory) available from [Internet Movie Script Database (IMSDb)](https://www.imsdb.com/).
  
  - Beam Search
  - Reranking the generated N-best list using a scoring function that linearly combines a length penalty and the log likelihood of the source given the target (Li et al. 2016) to avoid generated generic and commonplace responses such as I don’t know.

- Define PERSONA:
  - Character that an artificial agent, as actor, plays or performs during conversational interactions.
  - Composite of elements of identity (background facts or user profile), language behavior, and interaction style.

#### Notes

- For handling the issue of speaker consistency in neural response generation.
  - Speaker Model:
    - A speaker model encodes personas in distributed embeddings that capture individual characteristics such as background information and speaking style.
    - Models the personality of the respondent.
    - Embedding, which encodes speaker-specific information (e.g., dialect, register, age, gender, personal information) that influences the content and style of her responses.
  - Speaker-Addressee Model:
    - A dyadic speaker-addressee model captures properties of interactions between two interlocutors. Models the way the respondent adapts their speech to a given addressee — a linguistic phenomenon known as lexical entrainment (Deutsch and Pechmann, 1982).
    - Training persona vectors directly from conversational data and relevant side-information, and incorporating these directly into the decoder.

![Speaker Model](/images/speaker_model.png)

- The model learns speaker representations based on conversational content produced by different speakers, and speakers producing similar responses tend to have similar embeddings, occupying nearby positions in the vector space.
- The training data of speakers nearby in vector space help increase the generalization capability of the speaker model. Even if speaker
j was never asked the same question, this answer can help influence a good response from speaker j, and this without explicitly labeled geo-location information.
