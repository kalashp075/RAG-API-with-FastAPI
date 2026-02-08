# Build a RAG API with FastAPI

---

![Image](http://learn.nextwork.org/easygoing_purple_heroic_eel/uploads/ai-devops-api_g3h4i5j6)

### Key services and concepts

Services I used were: Python, Ollama, FastAPI, Chroma, tinyllama, and Swagger UI.

Key concepts I learnt include: building a RAG API, creating interactive API documentation, understanding production-ready APIs, local AI development, using a vector database for semantic search, and AI generation.

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
