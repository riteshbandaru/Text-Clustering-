# Sentence Clustering and Category Prediction

This code implements a sentence clustering and category prediction system using BERT embeddings, SpaCy for Named Entity Recognition (NER), and Agglomerative Clustering. The system can group similar sentences into clusters and predict categories for new sentences based on their content.

# The following Python libraries are used:

spacy

transformers

sklearn (scikit-learn)

torch

numpy

# The main components are:

BERTEmbedding: A class that uses BERT to convert sentences into vector representations.

extract_named_entities_and_keywords: A function that uses SpaCy to extract named entities and keywords from sentences.

cluster_sentences: A function that applies Hierarchical Clustering to group similar sentences.

extract_cluster_keywords: A function that extracts key terms for each cluster.

# How It Works

Sentence Embedding: The BERTEmbedding class uses a pre-trained BERT model to convert each sentence into a vector representation.

Named Entity Recognition and Keyword Extraction: The extract_named_entities_and_keywords function uses SpaCy to identify named entities (like persons, organizations, and locations) and extract meaningful keywords from each sentence.

Clustering: The cluster_sentences function applies Agglomerative Clustering to group similar sentences based on their BERT embeddings. It uses cosine distance as the similarity metric.

Cluster Analysis: The extract_cluster_keywords function identifies the most representative terms for each cluster by combining the named entities and keywords from all sentences in the cluster.

Category Prediction: For a new sentence, the system extracts named entities and keywords, which serve as potential categories for the sentence.

# Usage
To use this system, you can follow these steps:

Prepare a list of sentences you want to cluster.

Use the cluster_sentences function to group similar sentences.

Use the extract_cluster_keywords function to identify key terms for each cluster.

For a new sentence, use extract_named_entities_and_keywords to predict potential categories.

# Clustering Algorithm Choice
This code uses Hierarchical Clustering (Agglomerative Clustering) instead of K-means or DBSCAN for the following reasons:

1)No need to predefine cluster numbers

2)Produces interpretable dendrograms

3)Handles various cluster shapes

4)Consistent results

5)Works well with cosine similarity for sentence embeddings


While K-means might be faster for very large datasets and DBSCAN could identify noise points.

