# Crew-Agentic-RAG
Here is a well-structured `README.md` file for your GitHub repository. This document explains how to set up the environment, the purpose of the project, and how to use the code.

---

# Agentic RAG Using CrewAI & LangChain

This repository demonstrates how to integrate agents into a Retrieval-Augmented Generation (RAG) system using CrewAI and LangChain to retrieve relevant information effectively. The project utilizes multiple agents to perform routing, retrieval, relevance grading, and hallucination filtering to generate accurate and contextually grounded responses.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Requirements](#requirements)
- [Setup](#setup)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [License](#license)

## Overview

In this project, we explore how agents can enhance the RAG process. We use CrewAI for agent orchestration and LangChain for seamless language model integration. By combining agents for routing, retrieval, grading, and filtering, we create a dynamic pipeline that ensures relevant, accurate, and fact-based responses to user queries.

### Key Components
1. **Router Agent**: Decides whether to perform a vector search or a web search based on the input query.
2. **Retriever Agent**: Retrieves relevant documents from either the vector store or the web.
3. **Grader Agent**: Evaluates the relevance of the retrieved documents.
4. **Hallucination Grader**: Filters out hallucinated answers.
5. **Answer Grader**: Checks whether the final answer is useful and fact-based.

## Features

- Dynamic task routing using a Router agent.
- Retrieval from both vector stores (for embeddings) and web sources.
- Multi-step validation to ensure relevance and accuracy of the generated responses.
- Integrated PDF search using CrewAI's PDFSearchTool.

## Requirements

Before running this code, ensure that you have the following dependencies installed:

- Python 3.8 or higher
- `crewai==0.28.8`
- `crewai_tools==0.1.6`
- `langchain_community==0.0.29`
- `sentence-transformers`
- `langchain-groq`

You will also need API keys for Groq and Tavily.

## Setup

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/crew-agentic-rag.git
   cd crew-agentic-rag
   ```

2. **Install Dependencies**

   Run the following command to install the required libraries:

   ```bash
   pip install -r requirements.txt
   ```

3. **Set up API Keys**

   Make sure to add your Groq and Tavily API keys to your environment variables:

   ```bash
   export GROQ_API_KEY='your_groq_api_key'
   export TAVILY_API_KEY='your_tavily_api_key'
   ```

   Alternatively, you can add them to your `.bashrc`, `.zshrc`, or environment file.

4. **Download PDF Document**

   This code uses the paper *Attention Is All You Need* for retrieval tasks. The PDF is downloaded automatically from [NeurIPS proceedings](https://proceedings.neurips.cc/).

   ```bash
   wget https://proceedings.neurips.cc/paper_files/paper/2017/file/3f5ee243547dee91fbd053c1c4a845aa-Paper.pdf -O attention_is_all_you_need.pdf
   ```

## Usage

Once everything is set up, you can run the pipeline to ask a query and get a response from the agents.

1. **Kick Off the Pipeline**

   Modify the `inputs` dictionary to include your question:

   ```python
   inputs = {"question": "How does self-attention mechanism help large language models?"}
   ```

2. **Run the Code**

   You can then execute the notebook or the script:

   ```bash
   python crew-agentic.py
   ```

   The pipeline will retrieve relevant information, grade the results, and filter out hallucinated answers to provide a concise final response.

3. **Output**

   The final response will be printed to the console.

## Project Structure

```bash
.
├── README.md                 # Project documentation
├── crew-agentic.py           # Main script to run the agent pipeline
├── requirements.txt          # Python dependencies
└── attention_is_all_you_need.pdf  # Downloaded PDF used for RAG retrieval
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

This `README.md` file provides a clear guide for users to understand the project's purpose, set it up, and use it. Let me know if you need additional modifications!
