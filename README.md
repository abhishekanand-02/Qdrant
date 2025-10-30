"# Neural Search with Qdrant and Sentence Transformers

This project demonstrates how to build a powerful neural search system using Qdrant vector database and Sentence Transformers. The implementation showcases semantic search capabilities for finding similar content based on meaning rather than exact keyword matches.

## What is Neural Search?

Neural search is an advanced search paradigm that uses neural networks to understand the semantic meaning of queries and content, enabling more intelligent and contextual search results. Unlike traditional keyword-based search, neural search can:

- Understand context and meaning beyond exact word matches
- Handle synonyms and related concepts naturally
- Process queries in natural language
- Return semantically relevant results even when keywords don't match exactly

## About Qdrant

Qdrant is a vector similarity search engine designed for production usage. Key features include:

- High-performance vector similarity search
- Support for payload filtering
- ACID-compliant database
- Horizontal scalability
- Easy deployment with Docker
- Rich filtering capabilities
- Support for various distance metrics (cosine, euclidean, dot product)

## Semantic Search with Sentence Transformers

This project uses Sentence Transformers to convert text into meaningful vector embeddings. Key components:

- **Sentence Transformers**: State-of-the-art models for converting text into dense vector representations
- **Vector Embeddings**: High-dimensional numerical representations that capture semantic meaning
- **Similarity Search**: Finding similar content by comparing vector distances

## Project Structure

```
├── neural_search_qdrant_sentence_transformers.ipynb  # Main implementation notebook
├── requirements.txt                                  # Project dependencies
├── startup_vectors.npy                              # Saved vector embeddings
├── startups_demo.json                               # Sample dataset
└── qdrant_storage/                                  # Qdrant persistence directory
```

## Features

- Text-to-vector conversion using Sentence Transformers
- Vector storage and indexing with Qdrant
- REST API implementation using FastAPI
- Filtering capabilities by metadata
- Scalable vector search
- Docker support for easy deployment

## Getting Started

1. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

2. **Start Qdrant**
   ```bash
   docker pull qdrant/qdrant
   docker run -p 6333:6333 -v $(pwd)/qdrant_storage:/qdrant/storage qdrant/qdrant
   ```

3. **Run the API**
   ```bash
   python service.py
   ```

## Usage

1. **Vector Generation**
   - Load your text data
   - Convert to embeddings using Sentence Transformers
   - Store vectors in Qdrant

2. **Search API**
   - Send queries to `/api/search` endpoint
   - Receive semantically similar results
   - Apply filters for refined search

## Example Query

```bash
curl -X GET "http://localhost:8000/api/search?q=AI%20startups%20in%20healthcare"
```

## How It Works

1. **Text Encoding**: Converts text into vector embeddings using Sentence Transformers
2. **Vector Storage**: Stores embeddings in Qdrant with associated metadata
3. **Search Process**: 
   - Converts search query to vector
   - Finds nearest neighbors in vector space
   - Returns most similar results

## Use Cases

- Semantic document search
- Similar content recommendations
- Knowledge base search
- Content discovery
- Intelligent data retrieval

## Technologies Used

- Python 3.x
- Qdrant Vector Database
- Sentence Transformers
- FastAPI
- Docker
- NumPy
- Pandas

## Contributing

Feel free to submit issues and enhancement requests!

## License

This project is licensed under the MIT License - see the LICENSE file for details.

---

For more information:
- [Qdrant Documentation](https://qdrant.tech/documentation/)
- [Sentence Transformers Documentation](https://www.sbert.net/)
- [FastAPI Documentation](https://fastapi.tiangolo.com/)" 
