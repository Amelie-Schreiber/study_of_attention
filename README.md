# study_of_attention
A study of attention from many perspectives

In these notebooks we study:

- Permutation Equivariance of Self-Attention with LoRAs (without positional encodings)
- Translation Equivariance with LoRAs Proof (see [LoRA_equivariance](https://github.com/Amelie-Schreiber/study_of_attention/blob/main/LoRA_equivariance.ipynb))
- Designing General Group Equivariance of Lifting Self-Attention with LoRAs (see [LoRAs_lifting_self_attention](https://github.com/Amelie-Schreiber/study_of_attention/blob/main/LoRAs_lifting_self_attention.ipynb))
- Group Self-Attention Equivariance Proof Problem and Including LoRAs (see [LoRAs_group_self_attention](https://github.com/Amelie-Schreiber/study_of_attention/blob/main/LoRAs_group_self_attention.ipynb))
- For a complete proof of equivariance properties and LoRAs please see [GSA-Nets and LoRAs for TrOCR](https://github.com/Amelie-Schreiber/study_of_attention/blob/main/GSA_Nets_and_LoRAs_for_TrOCR.pdf)
- Computing pairwise distances between context vectors [context_and_ph_2](https://github.com/Amelie-Schreiber/study_of_attention/blob/main/context_and_ph_2.ipynb) note this could be important for understanding the following idea. Suppose we are given a phrase or collection of words that often occur together, then their pairwise distances (or a persistent homology clustering) should not change across contexts as much as if the words do not often occur together. More specifically, 
- [Topic Modelling and Natural Language Understanding with Persistent Homology](bert_english_ph_1.ipynb), see also [Topological Collocation and Keyword-Keyphrase Extraction](https://github.com/Amelie-Schreiber/study_of_attention/blob/main/context_persistent_homology_2.ipynb)
- Visualizing Attention Matrices and Graphs
- Basic Information Theory of Attention Probability Distributions
- Contextual Mappings and Context Vectors in GPT-2, Bert, and ViT
- Visualizing the Autoregressive Property of GPT-2
