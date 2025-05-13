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

## 📓 Notebook Overview: `map_creation.ipynb`

The notebook walks through the process of building a basic chatbot using LangGraph to perform Retrieval Augmented Generation. Key components include:

* **State Definition**: Utilizing Python's `TypedDict` to define the structure of the chatbot's state, which includes message history.

* **Node Creation**: Implementing nodes as functions that process input and update the state accordingly.

* **Graph Construction**: Assembling the nodes into a `StateGraph`, specifying the flow of data and control between nodes.

* **Execution**: Compiling and running the graph to simulate a conversation, demonstrating how the chatbot responds to user inputs.


## 🕸️ Graph Structure

The graph defined in `map_creation.ipynb` is a **stateful workflow** composed of modular nodes, each responsible for handling a specific part of the agent’s logic. Here's a high-level overview:

* **Input Node**: Receives user input and updates the conversation state.
* **Planner Node**: Uses a language model to generate a high-level plan based on the input.
* **Replanner Node**: Uses a language model to make sure the generated plan is right for the task and reformulates it when not.
* **Executor Node**: Executes the planned steps, potentially calling external tools or generating responses.
* **Parser**: Parses the output response of the Executor into a more suitable JSON format.
* **End Node**: Finalizes the output and returns a response.

The structure supports **iteration** and **looping**, allowing the planner and executor to alternate until the task is completed. This design mirrors how human reasoning unfolds across multiple steps rather than in a single shot.

---

## 🐞 Known Issues & Areas for Improvement

While the prototype demonstrates the core features of LangGraph, there are still open challenges and areas that require refinement:

* **⏱️ Time Requirements**:
  Currently, all steps are processed sequentially. Some tasks (e.g., tool invocations, plan steps) could be parallelized.
  ➤ **Suggested Fix**: Introduce an intermediate scheduling node before execution to manage task batching and parallelism.

* **🧠 Plan Coherence & Granularity**:
  The planner sometimes generates overly vague or under-specified plans, which hinders the executor's performance.
  ➤ **Suggested Fix**: Improve prompt engineering to request more structured and detailed plans from the LLM, potentially including numbered steps or explicit action types.


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
