# dES: A deep multimodal representation learning approach for denoising energy-based RNA secondary structure prediction and for discovering novel RNA (Draft)

What is dES:
- dES is a novel approach aimed at computing a robust representation of minimum free energy (MFE) structures, effectively mitigating the inherent noise in MFE predictions (F1 score on classification task; MFE: 0.82, dES for MFE: 0.92, validated structure: 0.94). This method is grounded in a denoising autoencoder architecture [1], which generates a stable representation of the minimum free energy structure by learning to reconstruct feature vectors of validated structures from those of MFE structures. These feature vectors are computed by integrating sequence and structural information using the n-motifs model [2]. The learned representation from MFE structures can be generalized to other related energy-based predicted structures, such as maximum expected accuracy and centroid structures.
  
- The model demonstrates the capability to identify sequences belonging to potential new RNA families. It achieves this by employing a deep nearest neighbors approach that distinguishes between in-distribution RNAs (belonging to a known family) and out-of-distribution RNAs (belonging to an unknown family) [3]. It's important to note that detecting samples from new families or classes is a well-recognized challenge in machine learning, akin to open set recognition (OSR) [4,5]. OSR involves a semantic shift in data distribution where, during testing, the model encounters samples from distinct unknown families.

Key Advantages of dES:
- Saves time and cost on experimental procedures for determining RNA secondary structures.
- Eliminates the need for experimental determination of secondary structures from known families, providing a denoised MFE representation closely aligned with validated structure representation.
- Focuses specifically on RNA sequences from potential novel families, enabling the detection of RNA sequences with limited structural knowledge.

Premiliminary results (Data : RFAM - 12 512 RNA, 56 families):
- F1 score on classification task (knn3); MFE : 0.82, dES train and test on MFE: 0.92,  validated structure: 0.94
- F1 score on classification task (knn3); MFE : 0.82, dES train and test on MFE: 0.92, Centroid : 0.80 , dES train on MFE and test on Centroid: 0.90, MEA : 0.82, dES train on MFE and test on MEA : 0.92 

- tsne visualization : raw MFE representation
<img src="https://github.com/jpsglouzon/denoising_mfe/assets/17144693/e841611b-6df2-41f6-bdc3-49d477accb72"  width="50%" height="50%">

- tsne visualization : dSE MFE representation
  
<img src="https://github.com/jpsglouzon/denoising_mfe/assets/17144693/5bfbdd3c-5388-4730-879a-21cc705ffae8"  width="50%" height="50%">

# References

[1] Vincent, Pascal, et al. "Extracting and composing robust features with denoising autoencoders." Proceedings of the 25th international conference on Machine learning. 2008.

[2] Glouzon, Jean-Pierre Séhi, Jean-Pierre Perreault, and Shengrui Wang. "The super-n-motifs model: a novel alignment-free approach for representing and comparing RNA secondary structures." Bioinformatics 33.8 (2017): 1169-1178.

[3] Sun, Yiyou, et al. "Out-of-distribution detection with deep nearest neighbors." International Conference on Machine Learning. PMLR, 2022.

[4] Yang, Jingkang, et al. "Generalized out-of-distribution detection: A survey." arXiv preprint arXiv:2110.11334 (2021).

[5] Yang, Jingkang, et al. "Openood: Benchmarking generalized out-of-distribution detection." Advances in Neural Information Processing Systems 35 (2022): 32598-32611.
