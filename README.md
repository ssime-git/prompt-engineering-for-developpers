# Prompt Engineering for developpers Challenges : Building a Memory-Enhanced AI Assistant Project

## 1. Project Overview

The Memory-Enhanced AI Assistant is an innovative project that aims to create an AI-powered chatbot capable of remembering and utilizing past conversations to provide more contextually relevant responses. This project combines natural language processing, vector databases, and machine learning to create a unique user experience.

The assistant will be able to:
- Engage in natural language conversations
- Store and recall information from past interactions
- Generate relevant search queries based on user input
- Provide contextually aware and personalized responses
- Respond to special commands for memory management

## 2. Project Objectives

1. Develop an AI assistant that can recall and utilize information from past conversations.
2. Implement a vector database for efficient storage and retrieval of conversation embeddings.
3. Create a system that can dynamically generate relevant search queries based on user input.
4. Build a user-friendly interface for interacting with the AI assistant.
5. Implement effective prompt engineering techniques to optimize AI interactions.

## 3. Technology Stack

- **Programming Language**: Python 3.7+
- **AI Model**: Ollama (with LLaMA3 model)
- **Vector Database**: Chroma
- **Relational Database**: PostgreSQL
- **Containerization**: Docker
- **Version Control**: Git
- **Additional Libraries**: psycopg, colorama, tqdm

## 4. Project Structure

```
memory_ai_assistant/
│
├── app/
│   ├── main.py
│   ├── database.py
│   ├── vector_db.py
│   ├── ai_model.py
│   └── utils.py
│
├── tests/
│   └── test_main.py
│
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
└── README.md
```

## 5. Key Components and Functions

### 5.1 Database Operations (database.py)

Functions to implement:
- `connect_db()`: Establish a connection to the PostgreSQL database.
- `fetch_conversations()`: Retrieve all stored conversations.
- `store_conversations(prompt, response)`: Save a new conversation to the database.
- `remove_last_conversation()`: Delete the most recent conversation.

### 5.2 Vector Database Operations (vector_db.py)

Functions to implement:
- `create_vector_db(conversations)`: Initialize and populate the Chroma vector database.
- `retrieve_embeddings(queries, results_per_query)`: Query the vector database for relevant embeddings.

### 5.3 AI Model Integration (ai_model.py)

Functions to implement:
- `stream_response(prompt)`: Generate and stream AI responses.
- `classify_embedding(query, context)`: Classify the relevance of embeddings.
- `create_queries(prompt)`: Generate search queries based on user input.

### 5.4 Main Application (main.py)

Functions to implement:
- `recall(prompt)`: Retrieve and process relevant past conversations.
- `main()`: The main loop handling user input and command processing.

### 5.5 Utilities (utils.py)

- Define constants and configuration parameters.
- Implement any helper functions as needed.

## 6. Prompt Engineering Focus Areas

### 6.1 System Prompt

Design a clear and concise system prompt that defines the AI assistant's personality, capabilities, and constraints. This prompt should instruct the AI to use past conversation data effectively without explicitly mentioning the recall process.

Example structure:
```python
system_prompt = (
    "You are an AI assistant with memory of past conversations. "
    "Use relevant past information to provide informed responses. "
    "Do not mention the recall process. Respond as a knowledgeable and helpful assistant."
)
```

### 6.2 Embedding Classification

Create prompts for the `classify_embedding` function that accurately assess the relevance of retrieved embeddings to the current query.

Example structure:
```python
classify_msg = (
    "You are an embedding classification agent. Given a query and a context, "
    "respond only with 'yes' if the context is highly relevant to the query, "
    "or 'no' if it is not directly related."
)
```

### 6.3 Query Generation

Develop prompts for the `create_queries` function that generate diverse and relevant search queries based on user input.

Example structure:
```python
query_msg = (
    "You are a search query generation agent. Create a Python list of search queries "
    "based on the given prompt. Focus on key concepts and potential related topics. "
    "Return only the Python list, no explanations."
)
```

### 6.4 Response Generation

While the main response generation uses the system prompt, consider adding context-specific instructions based on recalled information.

Example addition to response generation:
```python
context_instruction = (
    f"Consider the following relevant past information: {recalled_info}"
    "Incorporate this context into your response if applicable, but do not "
    "explicitly mention using past information."
)
```

## 7. Implementation Steps

1. Set up the project structure and Docker environment.
2. Implement database operations and test thoroughly.
3. Integrate the Chroma vector database and implement embedding functions.
4. Develop the AI model integration for response generation, embedding classification, and query creation.
5. Create the memory recall system.
6. Build the main application loop and command system.
7. Conduct prompt engineering for each AI interaction point.
8. Implement comprehensive error handling and logging.
9. Write unit tests for each component.
10. Optimize performance and fine-tune the system.

## 8. Special Commands

Implement the following special commands:
- `/recall [prompt]`: Explicitly trigger the memory recall for a given prompt.
- `/forget`: Remove the last conversation from memory.
- `/memorize [information]`: Explicitly store a piece of information in memory.

## 9. Testing and Evaluation

- Develop unit tests for each major function.
- Create a set of test conversations to evaluate memory recall accuracy.
- Assess the relevance and quality of generated responses.
- Measure system performance and response time.
- Evaluate the effectiveness of prompt engineering through A/B testing.

## 10. Challenges and Considerations

- Balancing between using past information and generating novel responses.
- Ensuring data privacy and security when storing conversation history.
- Optimizing vector search for large conversation databases.
- Fine-tuning prompts to achieve the desired AI behavior consistently.
- Handling potential biases in AI responses and recalled information.

## 11. Extensions and Future Work

- Implement user authentication for personalized experiences.
- Develop a web-based user interface.
- Integrate with external APIs for enhanced functionality.
- Implement conversation summarization to reduce token usage.
- Explore multi-modal interactions (e.g., image understanding).

## 12. Documentation and Reporting

- Maintain clear and concise code comments.
- Create a comprehensive README file with setup and usage instructions.
- Document prompt engineering efforts, including different versions and outcomes.
- Prepare a final project report detailing implementation, challenges, and results.

## 13. Conclusion

This Memory-Enhanced AI Assistant project offers a unique opportunity to explore the intersection of natural language processing, database management, and prompt engineering. By successfully implementing this system, students will gain valuable experience in creating AI-powered applications that can maintain context and provide more intelligent interactions.