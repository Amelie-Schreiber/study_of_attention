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
The pairwise distances between the context vectors of a collection of words reflect how the model understands the relationships between these words within a given context (sentence or paragraph). See also [bert_english_context_ph](https://github.com/Amelie-Schreiber/study_of_attention/blob/main/bert_english_context_ph.ipynb) and [bert_english_multilingual_context_ph](https://github.com/Amelie-Schreiber/study_of_attention/blob/main/bert_english_multilingual_context_ph.ipynb). Note that the performance of the multilingual version performs more poorly at preserving the topology of subsets corresponding to collocations or multiword expressions. This is also related to [these notebooks](https://github.com/Amelie-Schreiber/hebrew_context_persistent_homology) where we perform the same analysis on Hebrew texts with three different models. We find that the multilingual model also performs more poorly at preserving the topology of the context vectors for Hebrew as well. This is likely related to the lower level tokenization of the model and the difficulty in maintaining the topology of more tokens. 

1. **If the pairwise distances do not change in different contexts:**

    This could reflect a few things about the words and the model:
    
    * **Linguistic property:** It may suggest that the semantic relationships between the words are relatively stable across different contexts. This could be the case for words that have a fixed or limited set of meanings, or words that are strongly related to each other in some way.
    
    * **About the model:** It might indicate that the model is not sensitive to changes in context for these words, or that the specific layer and head selected does not encode context-sensitive information. GPT-2, like other transformers, is designed to capture context in its representations, but not all layers and heads capture this equally.

2. **If the pairwise distances change significantly in different contexts:**

    This could reflect a few things about the words and the model:
    
    * **Linguistic property:** It may suggest that the words have multiple meanings (polysemy) or that their semantic relationships are highly context-dependent. This could be the case for words that change their meaning based on the context they are used in.
    
    * **About the model:** It suggests that the model is sensitive to changes in context for these words, and that the specific layer and head selected are capturing this context-sensitive information. This would be expected behavior for a language model like GPT-2, which is designed to encode context in its representations.

Remember that the interpretation of these distances also depends on the layer and head chosen for the analysis. Different layers and heads of the model capture different types of information, so the same words may have different distances in different layers/heads. Moreover, we would expect certain collections of words to maintain their topology in many different contexts, such as collocations and multiword expressions. Other collections of words likely **should not** maintain their topology as we change their context. Having a model that is able to perform well in both cases is important to having a model that captures the semantic relationshipt between words of collocations or multiword expressions, and a model that is maximally expressive. With this in mind we may want to include both scenarios in the objective of the model. Note also, this applies to transformers with other modalities as well, such as vision transformers. 

- Visualizing Attention Matrices and Graphs
- Basic Information Theory of Attention Probability Distributions
- Contextual Mappings and Context Vectors in GPT-2, Bert, and ViT
- Visualizing the Autoregressive Property of GPT-2
