---
title: RankGen: Improving Text Generation with Large Ranking Models
authors: Kalpesh Krishna, Yapei Chang, John Wieting, Mohit Iyyer
year: 2022
tags:
  - LanguageModels
  - EBM
---

* We train RANKGEN using large scale contrastive learning to map a prefix close to the ground-truth sequence that follows it and far away from two types of negatives: (1) random sequences from the same document as the prefix, and (2) sequences generated from a large language model conditioned on the prefix.
* RANKGEN significantly outperforms decoding algorithms like nucleus, top-k, and typical sampling on both automatic metrics (85.0 vs 77.3 MAUVE) as well as human evaluations with English writers (74.5% human preference over nucleus sampling).
* ![[Screen Shot 2022-08-03 at 2.53.00 PM.png]]
* After model training, the dot product between the RANKGEN vectors of a prefix and a candidate continuation denotes their compatibility score. How can we integrate these scores into a decoding algorithm for text generation? We experiment with two strategies: 
	* (1) over-generation and reranking, in which we use any pretrained LM and existing decoding algorithm to generate multiple samples (20 in our experiments) and then re-rank them via RANKGEN scores; and 
	* (2) beam search (Figure 2), in which we generate N samples of length L via nucleus or ancestral sampling, compute the top B highest-scoring samples, and concatenate them to the prefix to continue generation.
* ![[Screen Shot 2022-08-03 at 2.54.54 PM.png]]