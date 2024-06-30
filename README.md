<img src="https://img.shields.io/badge/status-completed-green?logo=GitHub" alt="Completed"> 

# Introduction
Deeplearning.ai course on building vector database applications. Vector databases lets you input a collection of vectors, and that powers the 6 amazing applications we delve into in the course.

## Semantic Search
Using Sentence Transformers (a.k.a. SBERT) to compute embeddings. This unlocks a wide range of applications, including semantic search semantic textual similarity, and paraphrase mining. In Lesson 1, we did a Semantic Search.
1. Using a Quora question bank dataset we stored the indexes in  `Pinecone` which is our Vector Database (Serverless).
2. Query a sentence to the DB.
3. Get top X response from the DB.

## Retrieval Augmented Generation
Text embeddings are a NLP technique that converts textual data into numerical vectors that can be processed by machine learning algorithms, especially large models.
This application uses embeddings from OpenAI. OpenAI’s text embeddings measure the relatedness of text strings. 

Embeddings are commonly used for:
- **Search** (where results are ranked by relevance to a query string)
- **Clustering** (where text strings are grouped by similarity)
- **Recommendations** (where items with related text strings are recommended)
- **Anomaly detection** (where outliers with little relatedness are identified)
- **Diversity measurement** (where similarity distributions are analyzed)
- **Classification** (where text strings are classified by their most similar label)

An embedding is a vector (list) of floating point numbers. The [distance](https://platform.openai.com/docs/guides/embeddings/which-distance-function-should-i-use) between two vectors measures their relatedness. Small distances suggest high relatedness and large distances suggest low relatedness.

1. Asks a question to `Pincone`
2. `Pinecone` returns a long response
3. Perform prompt engineering and send to OpenAI
4. Get responses from OpenAI in a neat format

## Recommender Systems
Uses `langchain_text_splitters.character.RecursiveCharacterTextSplitter` where it splits text by recursively looking at characters. Recursively tries to split by different characters to find one that works.

1. Insert embeddings to `Pinecone`
2. Responses based on title search
3. Responses based on content search instead of titles

## Hybrid Search
Combine vectors (semantic search) with traditional text search with different modality. Uses Pinecone `BM25`

- BM25 is a **ranking function** that is used to retrieve text by estimating the relative importance of the terms in the text to the search query
- Calculated based on the number of documents in the data corpus and the word frequency across all relevant documents

Generate sparse and dense vectors for the full dataset and upsert these vectors with its metadata to Pinecone (BM25 -> Sparse | CLIP -> Dense)
- Modify the Alpha parameter to let it either be more dense or more sparse

## Facial Similarity Search
`PCA` or principal components analysis, reduces the dimensionality of any data. In this case, the data is the embeddings of many images. It helps s in visualizing and plotting our data by generating a new set of variables that represent all the mebeddings in our data.

`t-SNE` or t-Distributed Stochastic Neighbour Embedding, is a tool to visualize a high dimensional data like our data of multiple image embeddings. It works by grouping similar data points together based on their similarities in the higher dimensional space. This technique is highly effective for understanding complex datasets. It allows for identifying patterns and cluster and uncovering connections between data points that may not be immediately obvious in higher dimensions.

1. PCA: premiliminary step to reduce the dimension of our data of embeddings
2. T-SNE plot: to plot the data after PCA

PCA can get very expensive for large datasets!

## Anomaly Detection
Using Transformer based BERT

1. Sends for training using raw data
2. Validation sample against the model
3. Send embeddings to Pinecone
4. Searches for anomaly from the embeddings.

### Technology Stack
```Jupyter Notebooks, Pinecone```

### Core Concepts
`Databases`, `Vectors`, `Prompting`


[![GitHub Syahri](https://img.shields.io/github/followers/syahriikram?label=follow&style=social)](https://github.com/syahriikram)