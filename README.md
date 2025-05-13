# LangGraph Map Creation

This repository serves as an educational exploration into building dynamic and stateful AI agent workflows using [LangGraph](https://github.com/langchain-ai/langgraph), an extension of the LangChain ecosystem. The `map_creation.ipynb` notebook demonstrates how to construct a simple yet powerful chatbot by leveraging LangGraph's capabilities.

## 🧠 What is LangGraph?

LangGraph is a framework designed to facilitate the creation of complex, cyclical workflows for AI agents. Unlike traditional directed acyclic graphs (DAGs), LangGraph allows for loops and conditional transitions, enabling more sophisticated control flows in AI applications. This is particularly useful for tasks that require iterative reasoning, dynamic decision-making, or maintaining conversational context.

## 📁 Repository Structure

```
LangGraph-map-creation/
├── code/
│   └── map_creation.ipynb   # Main notebook demonstrating LangGraph usage
|   └── i_promessi_sposi.txt # File on which to do RAG
    └── concept_map.html     # created map
├── .gitignore
└── README.md
```

## 📓 Notebook Overview: `assignment.ipynb`

The notebook walks through the process of building a basic chatbot using LangGraph to perform Retrieval Augmented Generation. Key components include:

* **State Definition**: Utilizing Python's `TypedDict` to define the structure of the chatbot's state, which includes message history.

* **Node Creation**: Implementing nodes as functions that process input and update the state accordingly.

* **Graph Construction**: Assembling the nodes into a `StateGraph`, specifying the flow of data and control between nodes.

* **Execution**: Compiling and running the graph to simulate a conversation, demonstrating how the chatbot responds to user inputs.

## 🔧 Setup Instructions

To run the notebook locally, follow these steps:

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/AlbertoEusebio/LangGraph-map-creation.git
   cd LangGraph-map-creation/code
   ```

2. **Create a Virtual Environment** (optional but recommended):

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**:

   ```bash
   pip install langgraph langchain openai
   ```

4. **Set Up API Keys**:
   Ensure you have your OpenAI API key set as an environment variable in a ```.env``` file:

   ```bash
   OPENAI_API_KEY=<OPENAI_API_KEY>
   ```

5. **Launch Jupyter Notebook**:

   ```bash
   jupyter notebook
   ```

   Open `map_creation.ipynb` in the Jupyter interface to explore and run the chatbot example.

## 🧩 Key Concepts Demonstrated

* **State Management**: Maintaining conversational context across multiple interactions.

* **Graph-Based Workflow**: Defining flexible and dynamic control flows using LangGraph's `StateGraph`.

* **Node Modularity**: Encapsulating functionality within nodes for clarity and reusability.

* **Conditional Transitions**: Implementing logic to determine the next node based on current state or input.

## 📚 Further Reading

* [LangGraph Documentation](https://github.com/langchain-ai/langgraph)
* [LangChain Documentation](https://docs.langchain.com/)
* [OpenAI API Reference](https://platform.openai.com/docs)
