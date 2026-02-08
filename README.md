# Build a RAG API with FastAPI

---

![Image](http://learn.nextwork.org/easygoing_purple_heroic_eel/uploads/ai-devops-api_g3h4i5j6)

---

I'm doing this project to learn the concept of RAG (Retrieval-Augmented Generation) with modern framework such as FastAPI.

### Key services and concepts

Services I used were: Python, Ollama, FastAPI, Chroma, tinyllama, and Swagger UI.

Key concepts I learnt include: building a RAG API, creating interactive API documentation, understanding production-ready APIs, local AI development, using a vector database for semantic search, and AI generation.

### Challenges and wins

This project took me approximately 3 hours. The most challenging part was understanding the end-to-end process of how the RAG API works, from query to response, and troubleshooting common errors. It was most rewarding to see the RAG API successfully generate answers using my own knowledge base and having interactive documentation with Swagger UI.

### Why I did this project

I did this project because I wanted to learn how to build AI-powered APIs, specifically a RAG API, and understand the end-to-end process of how it works. I also wanted to gain hands-on experience with tools like FastAPI, Chroma, Ollama, and Swagger UI.

---

## Setting Up Python and Ollama

In this step, I'm setting up Python and Ollama. Python is the programming language... Ollama is AI model for running locally on my machine... I need these tools because RAG API will need both tools to be running.

### Python and Ollama setup

![Image](http://learn.nextwork.org/easygoing_purple_heroic_eel/uploads/ai-devops-api_i9j0k1l2)

### Verifying Python is working

### Ollama and tinyllama ready

Ollama is a tool that lets us run large language models locally on your own computer. Instead of sending requests to cloud services like OpenAI or Anthropic, Ollama runs the AI model directly on our machine.... I downloaded the tinyllama model because... The model will help my RAG API because it contains everything the AI needs to understand and generate text. When I run Ollama commands, it uses this model to answer your questions.

---

## Setting Up a Python Workspace

In this step, I'm setting up a workspace... I need it to keep everything organized in one place makes it easier to manage my project and find files when I need them.

### Python workspace setup

### Virtual environment

A virtual environment is an isolated Python environment that keeps my project's dependencies separate from other Python projects on my computer.... I created one for this project to  keeps my project's tools and packages separate, so nothing I do here will break other Python programs on my computer. Once I activate it (venv) prefix in my prompt is a visual reminder that you're I am now using the virtual environment's Python and packages. To create a virtual environment, I executed the command python3 -m venv venv

### Dependencies

The packages I installed are fastapi, uvicorn, chromadb, an ollama... FastAPI is used for handleing all the networking and routing logic. Chroma is used for storing document embeddings (numerical representations of text). Uvicorn is used for running my FastAPI app and makes it accessible locally on your computer. Ollama lets me code talk to Ollama.

![Image](http://learn.nextwork.org/easygoing_purple_heroic_eel/uploads/ai-devops-api_u1v2w3x4)

---

## Setting Up a Knowledge Base

In this step, I'm creating a knowledge base. A knowledge base is repository of information that provides accurate and up-to-date data on specific topics. It's a collection of documents or text that my AI model (like tinyllama) can search through to find relevant information. I need it to provide AI models with accurate, up-to-date, and specific information beyond their initial training data, enabling relevant retrieval for RAG.

### Knowledge base setup

![Image](http://learn.nextwork.org/easygoing_purple_heroic_eel/uploads/ai-devops-api_t1u2v3w4)

### Embeddings created

Embeddings are numerical representations of text that capture meaning. Words with similar meanings are placed close together, while unrelated words are far apart. I created them by running the embedding script. The db/ folder contains knowledge base's embeddings so Chroma can quickly search through them when your API is running. This is important for RAG because this is what makes RAG work: finding relevant context based on meaning, not just exact word matches.

---

## Building the RAG API

In this step, I'm building a RAG API. An API is a set of rules and tools that allows different software applications to communicate and interact with each other. FastAPI is a modern Python web framework for building APIs. It's designed to be fast, easy to use, and automatically generates interactive documentation. Companies like Uber, Netflix, and Microsoft use FastAPI for their APIs.

### FastAPI setup

### How the RAG API works

My RAG API works as:

1. Question arrives: Someone sends a question to your API at /query
2. Search my documents: Chroma searches through my knowledge base to find text that matches the question's meaning
3. Get matching text: Chroma returns the most relevant information from my documents (this is called "context")
4. Generate answer: The question and the matching text are sent together to tinyllama, which creates an answer
5. Send back the answer: The answer is sent back to me

![Image](http://learn.nextwork.org/easygoing_purple_heroic_eel/uploads/ai-devops-api_f3g4h5i6)

---

## Testing the RAG API

In this step, I'm testing my RAG API. I'll test it using SwaggerUI.  Swagger UI is an automatically generated, interactive documentation page for my FastAPI server. It lets me visually explore my API's endpoints, see what parameters they accept, and even try them out right from my browser - no special tools or coding required. I'll use it to explore and test my API visually in my browser.

### Testing the API

### API query breakdown

I queried my API by running the command "curl -X POST "http://127.0.0.1:8000/query" -G --data-urlencode "q=What is Kubernetes?"". The command uses the POST method, which means I am sending data to the server. The API responded with  a JSON object containing the answer to my query.

![Image](http://learn.nextwork.org/easygoing_purple_heroic_eel/uploads/ai-devops-api_g3h4i5j6)

### Swagger UI exploration

Swagger UI is an automatically generated, interactive documentation page for the FastAPI server. ... I used it to test my API by entering a question like "What is Kubernetes?" in the q parameter field and clicking "Execute". The best part about using Swagger UI was that it provided a visual and interactive way to test API endpoints directly in the browser, making it much easier than manual curl commands.

---

---

---
