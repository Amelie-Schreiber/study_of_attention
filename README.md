# study_of_attention
A study of attention from many perspectives

In these notebooks we study:

- Permutation Equivariance of Self-Attention with LoRAs (without positional encodings)
- Translation Equivariance with LoRAs Proof (see [LoRA_equivariance](https://github.com/Amelie-Schreiber/study_of_attention/blob/main/LoRA_equivariance.ipynb))
- Designing General Group Equivariance of Lifting Self-Attention with LoRAs (see [LoRAs_lifting_self_attention](https://github.com/Amelie-Schreiber/study_of_attention/blob/main/LoRAs_lifting_self_attention.ipynb))
- Group Self-Attention Equivariance Proof Problem and Including LoRAs (see [LoRAs_group_self_attention](https://github.com/Amelie-Schreiber/study_of_attention/blob/main/LoRAs_group_self_attention.ipynb))
- For a complete proof of equivarianc properties and LoRAs please see [GSA-Nets and LoRAs for TrOCR](https://github.com/Amelie-Schreiber/study_of_attention/blob/main/GSA_Nets_and_LoRAs_for_TrOCR.pdf)
- Computing pairwise distances between context vectors [context_and_ph_2](https://github.com/Amelie-Schreiber/study_of_attention/blob/main/context_and_ph_2.ipynb) note this could be important for understanding the following idea. Suppose we are given a phrase or collection of words that often occur together, then their pairwise distances (or a persistent homology clustering) should not change across contexts as much as if the words do not often occur together. More specifically, 
- Collocation and keyword-keyphrase extraction using persistent homology of the context vectors of a single attention head (see [context_persistent_homology_2](https://github.com/Amelie-Schreiber/study_of_attention/blob/main/context_persistent_homology_2.ipynb))
The pairwise distances between the context vectors of a collection of words reflect how the model understands the relationships between these words within a given context (sentence or paragraph). 

1. **If the pairwise distances do not change in different contexts:**

    This could reflect a few things about the words and the model:
    
    * **Linguistic property:** It may suggest that the semantic relationships between the words are relatively stable across different contexts. This could be the case for words that have a fixed or limited set of meanings, or words that are strongly related to each other in some way.
    
    * **About the model:** It might indicate that the model is not sensitive to changes in context for these words, or that the specific layer and head selected does not encode context-sensitive information. GPT-2, like other transformers, is designed to capture context in its representations, but not all layers and heads capture this equally.

2. **If the pairwise distances change significantly in different contexts:**

    This could reflect a few things about the words and the model:
    
    * **Linguistic property:** It may suggest that the words have multiple meanings (polysemy) or that their semantic relationships are highly context-dependent. This could be the case for words that change their meaning based on the context they are used in.
    
    * **About the model:** It suggests that the model is sensitive to changes in context for these words, and that the specific layer and head selected are capturing this context-sensitive information. This would be expected behavior for a language model like GPT-2, which is designed to encode context in its representations.

Remember that the interpretation of these distances also depends on the layer and head chosen for the analysis. Different layers and heads of the model capture different types of information, so the same words may have different distances in different layers/heads.

- Visualizing Attention Matrices and Graphs
- Basic Information Theory of Attention Probability Distributions
- Contextual Mappings and Context Vectors in GPT-2, Bert, and ViT
- Visualizing the Autoregressive Property of GPT-2
