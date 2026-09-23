# RAG-Based HR Assistant

A Retrieval-Augmented Generation (RAG) based HR Assistant that answers employee-related questions using information retrieved from an HR/employee handbook PDF.

The application retrieves relevant information from the uploaded document and generates answers based on that context, helping users quickly find HR policies and company-related information.

## Features

* Ask HR-related questions in natural language
* Retrieve relevant information from an employee handbook
* Generate context-based answers using an LLM
* PDF document-based question answering
* Semantic search using vector embeddings
* Simple web interface using Gradio
* Similarity threshold to improve retrieval relevance

## Tech Stack

* **Python**
* **LangChain** – RAG pipeline and document processing
* **ChromaDB** – Vector database for storing document embeddings
* **MiniLM** – Text embedding model
* **FLAN-T5** – Language model for generating answers
* **Gradio** – User interface
* **Google Colab** – Development and execution environment

## How It Works

The project follows a basic RAG pipeline:

```text
Employee Handbook PDF
        ↓
Document Loading
        ↓
Text Splitting
        ↓
Text Embeddings (MiniLM)
        ↓
ChromaDB Vector Store
        ↓
User Question
        ↓
Similarity Search
        ↓
Relevant Context
        ↓
FLAN-T5
        ↓
Generated Answer
```

## Project Workflow

1. The HR handbook PDF is loaded into the application.
2. The document is divided into smaller text chunks.
3. Each chunk is converted into a vector embedding using MiniLM.
4. The embeddings are stored in ChromaDB.
5. When a user asks a question, the question is converted into an embedding.
6. ChromaDB retrieves the most relevant document chunks.
7. Retrieved information is provided as context to FLAN-T5.
8. The model generates an answer based on the retrieved context.

## Retrieval Threshold

A similarity threshold of **0.55** is used during retrieval to help filter out less relevant results.

This helps the system avoid generating answers from document sections that are not sufficiently related to the user's question.

## Example Questions

The assistant can be used for questions such as:

* What is the company's leave policy?
* How many casual leaves are available?
* What is the work-from-home policy?
* What are the working hours?
* What is the employee termination policy?
* What benefits are provided to employees?

The actual answers depend on the information available in the uploaded HR handbook.

## Installation

Clone the repository:

```bash
git clone <your-repository-link>
cd <project-folder>
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Run the application in Google Colab or the configured Python environment.

## Requirements

Create a `requirements.txt` file containing the libraries used by the project, for example:

```text
langchain
chromadb
sentence-transformers
transformers
gradio
pypdf
```

Depending on the implementation, additional LangChain integration packages may be required.

## Project Structure

```text
RAG-HR-Assistant/
│
├── HR_Chatbot.ipynb
├── requirements.txt
├── README.md
└── employee_handbook.pdf
```

## Limitations

* The assistant can only answer questions based on the information available in the provided HR document.
* It may produce incorrect answers if the retrieved context is incomplete or unclear.
* The quality of responses depends on the document, retrieval quality, and language model.
* It is not intended to replace official HR guidance.

## Future Improvements

* Support multiple HR documents
* Add conversation history
* Improve document chunking and retrieval
* Add authentication for employees
* Use a stronger embedding or language model
* Add source references to retrieved answers
* Deploy the application as a web application

## Author

**Utkarsh Jaiswal**

B.Tech Computer Science & Engineering
