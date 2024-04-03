# Evaluation for Retrieval
Recall@1 0.86 \
Recall@10 0.57 \    
Recall@100 0.57 \
MRR 0.40

# Model Evaluation (SEP token) (Deberta Fine tuned)
Accuracy 0.73 \
MicroF1 0.52 \

# Model Evaluation (Bi encoder bert, krlng/sts-BERT-bi-encoder)
Accuracy 0.63 \
MicroF1 0.46 \


# Models
Retriever is multi-qa-MiniLM-L6-cos-v1. NLI model is DebertaV3/Bert-bi-encoder. 
Retriever Emb dim is 384. \
Retriever is finetuned via contrastive learning (random negative samples). NLI Model is fine tuned on training dataset. 

# Corpus indexing
Used faiss to index document level encodings. Reranking didnt seem necessary. \
To find relevant sentences, first top k docs were retrived. Then per doc, every sentence was ranked.\
 We take the best k sentences from the entire retrieved doc set. k = 5 in our case

# NLI
A linear layer was added on top of Deberta/bert when required, projecting mean pooled embeddings.
