# Chatty_Web

Developed a project that analyzes websites to retrieve relevant information based on user requests, utilizing the Retrieval-Augmented Generation (RAG) pipeline. This approach efficiently pinpoints key details while enabling flexible and natural language queries

This repository contains code for a RetrievalQA chain using Langchain to answer questions about websites.

# Dependencies:

* langchain
* sentence-transformers
* chromadb

# Installation:

```pip install langchain sentence-transformers chromadb```
Use code with caution.

# Running the script:

* Place the script you provided in the main directory of your repository.
* Make sure you have a Hugging Face API token and update the getpass line accordingly.
* Replace the website URL in the URL variable with the desired website.
* Run the script by typing python your_script_name.py in your terminal.

# Code Breakdown:

The script performs the following steps:

# Data Loading and Processing:

* Loads the content of a website using WebBaseLoader.
* Splits the content into smaller chunks using RecursiveCharacterTextSplitter.

# Embedding Generation:

*** Prioritize API usage: *** Attempts to generate word embeddings for each text chunk using the specified pre-trained language model through the Hugging Face Inference API.
*** Local fallback (if rate limit exceeded):*** If the API rate limit is reached, the script automatically attempts to download the entire model locally and use it for embedding generation. This process might take some time depending on the model size and your internet connection.
* Stores the embeddings in a vectorstore using ChromaDB.
* Large Language Model Setup:
* Loads a large language model from Hugging Face Hub.

# Retrieval Step:

Finds relevant documents from the vectorstore based on the user's query using mmr search.
* Augmentation Step:
Creates a prompt for the LLM with instructions and the user's query.
* Generation Step:
Uses the LLM to generate an answer based on the prompt and retrieved information.

# Contributing:

Feel free to fork this repository and make your own contributions. Pull requests are welcome!

# Additional Notes:

You can adjust the parameters of the LLM and search strategy to optimize the results.
This is a basic example, and you can extend it to handle more complex tasks like summarizing information or creating different types of content.
Be aware that downloading large models locally can consume significant storage space and bandwidth.
