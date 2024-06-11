# Langchain Chatbots with Multiple LLMs

This project demonstrates the creation of chatbots using the Langchain library, integrating different AI models including OpenAI, Ollama, and Groq, and deploying the application using Streamlit.

## Index

- [Project Description](#project-description)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [File Descriptions](#file-descriptions)
- [Detailed Description of Components](#detailed-description-of-components)

## Project Description

This project consists of three separate chatbot applications, each utilizing a different AI model (OpenAI, Ollama, and Groq) to demonstrate how Langchain can be used to build powerful and responsive chatbots. The applications are built with Streamlit for a simple and interactive user interface.

## Prerequisites

- Python 3.7+
- Streamlit
- Langchain
- OpenAI API Key
- Ollama
- Open Source LLM Model downloaded locally
- Groq API Key

## Installation

1. Create and activate a virtual environment:
    ```bash
    python -m venv .venv
    source .venv/bin/activate  # On Windows, use `.venv\Scripts\activate`
    ```

2. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Configuration

1. Create a `.env` file in the project root directory and add your API keys:
    ```
    OPENAI_API_KEY=your_openai_api_key
    LANGCHAIN_API_KEY=your_langchain_api_key
    GROQ_API_KEY=your_groq_api_key
    LANGCHAIN_PROJECT="project_name" 
    ```
    - Create account on smith.langchain.com -> create project -> add that project name here to LANGCHAIN_PROJECT
    - This tracks all the conversation with the models, time required for response and cost if its paid model
## Running the Application

To run the chatbot applications using Streamlit, execute the following command:

```bash
streamlit run <filename>.py
```

Replace `<filename>` with `openai_chatbot.py`, `ollama_chatbot.py`, or `groq_chatbot.py` depending on which chatbot you want to run.

## File Descriptions

- `openai_chatbot.py`: Contains the implementation for the chatbot using OpenAI's GPT-3.5-turbo model.
- `ollama_chatbot.py`: Contains the implementation for the chatbot using Ollama's Llama3 model.
- `groq_chatbot.py`: Contains the implementation for the chatbot using Groq's mixtral-8x7b-32768 model.
- `.env`: File to store API keys and environment variables.
- `requirements.txt`: File listing all the required Python packages.

## Detailed Description of Components

### Streamlit

Streamlit is an open-source app framework used to create interactive web applications. It allows you to build and deploy powerful data apps quickly and easily.

### Langchain

Langchain is a library designed to facilitate the creation of advanced language models and conversational AI applications. It supports integration with various AI models and provides tools for managing chat prompts, output parsing, and conversation memory.

### ChatOpenAI

`ChatOpenAI` is a class from the `langchain_openai` module used to interact with OpenAI's language models. In this project, it is used to create a chatbot using the GPT-3.5-turbo model.

### ChatPromptTemplate

`ChatPromptTemplate` is used to create chat prompts that structure the input data for the AI models. It helps in defining the format and context of the questions asked by users.

### StrOutputParser

`StrOutputParser` is used to parse the responses from the AI models into a string format that can be displayed to the user.

### Ollama

Ollama is another AI model used in this project. The `Ollama` class from the `langchain_community.llms` module is used to interact with this model.

### Groq

Groq is an AI model known for its high performance. The `ChatGroq` class from the `langchain_groq` module is used to interact with this model.

### dotenv

`dotenv` is a library used to load environment variables from a `.env` file into your Python application. It helps in keeping sensitive information like API keys secure.

## Code Explanation
### OpenAI and Ollama Chatbot

The OpenAI and Ollama chatbot implementations start by importing necessary libraries and loading environment variables from a `.env` file. The `ChatPromptTemplate` is used to define the prompt structure, and `StrOutputParser` parses the AI's responses. A `ChatOpenAI` or `Ollama` object is created to interact with the respective AI model. The chatbot takes user input via a text field in Streamlit, sends the input to the model, and displays the response.

### Groq Chatbot

The Groq chatbot also begins by importing necessary libraries and loading environment variables. It initializes a `ConversationBufferWindowMemory` to store the chat history and uses `ChatGroq` to interact with the Groq model. The chatbot collects user input via a text field, processes the input through the conversation chain, and displays the AI's response. It maintains the chat history to provide context for ongoing conversations.

### Langchain Overview

Langchain simplifies the process of building conversational AI applications by providing abstractions for managing prompts, parsing outputs, and maintaining conversation context. In this project, Langchain integrates with various AI models (OpenAI, Ollama, Groq) to handle the complexity of natural language understanding and generation. The library allows for the seamless combination of prompt templates, language model interactions, and output parsing, making it easier to build and deploy chatbots.

---

### requirements.txt

```plaintext
langchain-openai
langchain-core
python-dotenv
streamlit
langchain-community
```

