# HeTDR
Drug repositioning based on Heterogeneous network and Text Mining

### 'Get drug feature' directory
1. 'data' directory Contain the nine drug-related networks.
2. compute_similarity.m compute Jaccard similarity based on association network(i.e., drug-disease, drug-side-effect, and drug-protein networks)
3. PPMI_Matrix.m generate PPMI matrix
4. fuse_similarity_matrix.m fuse nine PPMI matrix
5. SAE.py get the drug feature

### 'Get disease feature' directory
Part of codes and parameters use the BioBERT (https://github.com/dmis-lab/biobert)
1. Requirments: tensorflow-gpu  >= 1.11.0   GPU version of TensorFlow.
                sklearn                     To evaluate RE answers
                pandas==0.23
2. Fine-tuning BioBERT: Relation Extraction (RE)
   Run Shell File train.sh    # Remind of the file path. Detail see https://github.com/dmis-lab/biobert
   (After that, we get the embedding of vocabularies, which we need to obtain the model checkpoint file, i.e. model.ckpt-4496.)
3. getEmbedding_1229.py get the Embedding of diseases: Run Code File getEmbedding_1229.py  

### 'link_prediction'  directory
1. 'data' directory contain the gold standard drug-disease association and the example dataset.
2. main.py get the result of disease-drug association prediction.
   You can use `python main.py --input data  --features data/feature`
