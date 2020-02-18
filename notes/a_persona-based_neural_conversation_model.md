
## [A Persona-Based Neural Conversation Model](https://arxiv.org/abs/1603.06155)

###### TLDR;



#### Key Points

- Seq2Seq
- Twitter dataset
- Define PERSONA:
  - Character that an artificial agent, as actor, plays or performs during conversational interactions.
  - Composite of elements of identity (background facts or user profile), language behavior, and interaction style.

#### Notes

- For handling the issue of speaker consistency in neural response generation.
  - A speaker model encodes personas in distributed embeddings that capture individual characteristics such as background information and speaking style.
  - A dyadic speaker-addressee model captures properties of interactions between two interlocutors.
  - Training persona vectors directly from conversational data and relevant side-information, and incorporating these directly into the decoder.

![Speaker Model](/images/speaker_model.png)
Source: ![Image](https://arxiv.org/pdf/1603.06155.pdf)
