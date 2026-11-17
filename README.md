# Doc-GenAi

A notebook that answers questions about a PDF document using retrieval-augmented generation (RAG) with LangChain, Azure OpenAI and Chroma.

## How it works

1. Load the PDF (`Customer Information.pdf`) with `PyPDFLoader`.
2. Split it into chunks of about 1,000 characters.
3. Create embeddings for each chunk with an Azure OpenAI embedding deployment.
4. Store the embeddings in a Chroma vector store.
5. Ask a question; the most relevant chunks are retrieved and passed to the model to produce the answer.

## Files

| File | Purpose |
|---|---|
| `GenAi - Copy.ipynb` | The notebook |
| `Customer Information.pdf` | Sample document to query |
| `Customer Information.docx` | Source of the sample document |

## Requirements

- Python 3.9+
- An Azure OpenAI resource with an embedding deployment and a chat or completion deployment

```bash
pip install openai langchain chromadb pypdf
```

## Usage

1. Open the notebook in Jupyter or VS Code.
2. Replace the placeholders with your own values: Azure endpoint, API key, API version and deployment name.
3. Run the cells in order, then set `query` to your question.

Keep your API key out of the notebook when you commit; load it from an environment variable instead.

## Notes

The notebook was written against an older LangChain API (`VectorDBQA`, `langchain.embeddings`). With current LangChain releases some imports have moved and may need updating.
