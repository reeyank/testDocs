---
id: Usage.Searching Stored Memories
title: Searching Stored Memories
---
# Searching Stored Memories
# Usage

## Searching Stored Memories

This section explains how to search through stored document memories using semantic similarity queries. The system leverages vector embeddings and ChromaDB to retrieve contextually relevant results.

---

### How It Works
1. **Query Processing**:  
   User-provided search terms are converted into vector embeddings using the same model that processed stored documents.
2. **Similarity Search**:  
   The `VectorStore` component compares query embeddings against stored document chunks via cosine similarity.
3. **Ranked Results**:  
   Matches are returned in descending order of relevance, with similarity scores indicating match confidence.

```mermaid
graph LR
    A[Search Query] --> B(Embedding Conversion)
    B --> C[Similarity Search]
    C --> D{Top N Results}
    D --> E[Ranked Memories]
```

---

### CLI Command Example
```bash
# Search across all agent memories
agent memory search "blockchain scalability solutions"

# Sample output
[Memory ID: 789] Similarity: 0.82 | Category: tech
"Sharding improves Ethereum scalability by partitioning the network..."
```

> [!NOTE]  
> Lower absolute similarity scores (e.g., 0.4-0.6) are normal with small datasets. Relative ranking matters more - the top result is always the most semantically relevant match.

---

### Best Practices
1. Use natural language queries instead of keywords:
   - ✅ "How does proof-of-stake work?"
   - ❌ "POS mechanism"
2. Combine with [memory browsing](link-to-list-section) to verify context
3. Add more documents through [bulk upload](link-to-upload-section) to improve score reliability

---

### Advanced Options
| Parameter      | Description                          | Default |
|----------------|--------------------------------------|---------|
| `--threshold`  | Minimum similarity score (0.0-1.0)   | 0.3     |
| `--categories` | Filter by comma-separated categories| all     |
| `--limit`      | Maximum results to return           | 10      |

Example using filters:
```bash
agent memory search "zero-knowledge proofs" --categories cryptography --threshold 0.45
```

---

This search system forms the foundation for agent recall capabilities. Results directly influence responses in [CLI chat interactions](link-to-cli-section), with the agent automatically incorporating top-matched memories into its context window.
