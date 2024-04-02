# Evaluation
Recall@1 0.86 \
Recall@10 0.57 \    
Recall@100 0.58 \
MicroF1 0.47 \

# Models
Retriever is multi-qa-MiniLM-L6-cos-v1. NLI model is DebertaV3. 
Retriever Emb dim is 384. \
Retriever is finetuned via contrastive learning (random negative samples). NLI Model is fine tuned on training dataset. 

# Corpus indexing
Used faiss to index document level encodings. Reranking didnt seem necessary. \
To find relevant sentences, first top k docs were retrived. Then per doc, every sentence was ranked.\
 We take the best k sentences from the entire retrieved doc set. k = 5 in our case

 # NLI
 A linear layer was added on top of Deberta, projecting mean pooled embeddings. Gave validation accuracy of 0.93
