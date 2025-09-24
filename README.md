# NASA-AstroSearch

A search engine for NASA's Astronomy Picture of the Day (APOD) dataset, built with Elasticsearch and modern search techniques.

## What it does

Search through thousands of NASA astronomy images and descriptions using:
- **Text search** - Standard keyword matching
- **Smart search** - N-gram tokenization for partial matches  
- **Semantic search** - AI-powered meaning-based search using sentence transformers

## Tech Stack

- **Elasticsearch** - Core search engine with multiple indexing strategies
- **FastAPI** - REST API backend
- **Sentence Transformers** - Semantic embeddings for AI search

## Features

- Multiple search modes (text, semantic, hybrid)
- Year-based filtering 
- Search result aggregation and analytics
- GPU-accelerated embedding generation
- HTML content preprocessing

## Quick Start

1. Start Elasticsearch:
   ```bash
   docker run -p 9200:9200 -e "discovery.type=single-node" elasticsearch:7.x
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Index the data:
   ```bash
   python index_data.py
   python index_data_embedding.py
   ```

4. Start the API:
   ```bash
   uvicorn main:app --reload
   ```

## API Endpoints

- `GET /api/v1/regular_search/` - Standard text search
- `GET /api/v1/semantic_search/` - AI-powered semantic search  
- `GET /api/v1/get_docs_per_year_count/` - Search analytics