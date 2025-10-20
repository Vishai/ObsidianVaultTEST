# Retrieval Augmented Generation (RAG)

## Concept

RAG combines language model generation with information retrieval. Instead of relying solely on training data, the model fetches relevant information at query time.

## Why RAG?

### Problems It Solves

1. **Knowledge Cutoffs**: Access to current information
2. **Hallucination**: Ground responses in retrieved facts
3. **Domain Specificity**: Incorporate specialized knowledge
4. **Transparency**: Can cite sources

### Traditional LLM Limitations

- Training data becomes stale
- Can't access private/proprietary information
- Struggles with very specific facts
- No source attribution

## Architecture

```
Query → Retrieval → Augmentation → Generation → Response
```

### 1. Retrieval Stage

**Vector Search**
- Convert query to embedding
- Search vector database
- Retrieve top-k similar documents

**Hybrid Search**
- Combine semantic and keyword search
- Better coverage

### 2. Augmentation Stage

- Format retrieved documents
- Add to prompt context
- Provide source metadata

### 3. Generation Stage

- LLM generates response
- Uses retrieved context
- Cites sources when appropriate

## Implementation Patterns

### Naive RAG
Simple: retrieve → stuff into prompt → generate

### Advanced RAG
- Query rewriting
- Multi-step retrieval
- Relevance filtering
- Context compression
### Agentic RAG
- Multi-turn retrieval
- Self-correction
- Tool use for verification

## Technical Components

### Vector Databases
- Pinecone
- Weaviate
- Chroma
- Qdrant

### Embedding Models
- OpenAI ada-002
- Sentence Transformers
- Cohere embeddings

### Chunking Strategies
- Fixed size (e.g., 512 tokens)
- Semantic splitting (paragraphs)
- Recursive character splitting
- Sliding windows with overlap

## Optimization Techniques

### Improve Retrieval
- Better embeddings
- Hybrid search
- Query expansion
- Metadata filtering

### Improve Generation
- Prompt engineering
- Context compression
- Reranking results
- Citation formatting

## Challenges

1. **Retrieval Quality**: Garbage in, garbage out
2. **Context Window**: Limited space for retrieved docs
3. **Latency**: Retrieval adds time
4. **Cost**: Vector DB + LLM calls
5. **Stale Indices**: Need regular updates

## Real-World Applications

- Customer support bots
- Research assistants
- Documentation Q&A
- Legal document analysis
- Medical literature search

---
*Related: [[llm_agents|LLM Agents]] | [[../../02_Projects/Project_Phoenix/overview|Project Phoenix]]*
