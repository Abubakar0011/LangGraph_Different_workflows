### Different LangGraph Workflows along with Humman In The Loop

This repository contains a collection of Jupyter notebooks demonstrating advanced patterns and workflows using **LangGraph**, a library for building stateful, multi-actor applications with Large Language Models (LLMs). Each notebook focuses on a specific architectural pattern, showcasing how to design and implement complex LLM interactions.

## Table of Contents

1.  [Introduction](#introduction)
2.  [Notebooks Overview](#notebooks-overview)
    * [Orchestrator-Worker](#orchestrator-worker)
    * [Parallelization](#parallelization)
    * [Prompt Chaining](#prompt-chaining)
    * [Routing](#routing)
    * [Evaluator-Optimizer](#evaluator-optimizer)
    * [Human-in-the-Loop](#human-in-the-loop)
3.  [Setup and Installation](#setup-and-installation)
4.  [Usage](#usage)
5.  [Contributing](#contributing)
6.  [License](#license)

---

## 1. Introduction

LangGraph extends LangChain to enable the creation of cyclical graphs, allowing for more complex, stateful, and dynamic LLM applications. This collection explores common and powerful patterns that go beyond simple sequential chains, including:

* **Orchestration:** Central LLMs breaking down tasks and delegating.
* **Parallelism:** Executing multiple LLM calls concurrently.
* **Structured Output:** Guiding LLMs to produce predictable data formats.
* **Conditional Routing:** Dynamically changing workflow paths based on LLM decisions.
* **Iterative Refinement:** Using LLMs to evaluate and improve previous outputs in a loop.
* **Human Intervention:** Incorporating human feedback and decision-making into the loop.

Each notebook provides a practical example of how these patterns can be implemented.

---

## 2. Notebooks Overview

### Orchestrator-Worker

* **File:** `Orchestrator_worker_Langgraph.ipynb`
* **Concept:** Demonstrates an "Orchestrator-Worker" workflow where a central LLM breaks down a task and delegates sub-tasks to parallel worker LLMs, then synthesizes their results.
* **Key Features:** Dynamic task decomposition, parallel LLM execution, state aggregation.
* **Use Case:** Generating multi-section reports or complex content.

### Parallelization

* **File:** `Parallelization.ipynb`
* **Concept:** Highlights how to run multiple independent LLM calls concurrently within a LangGraph workflow to speed up overall processing.
* **Key Features:** Concurrent LLM execution, efficient state updates from parallel branches.
* **Use Case:** Accelerating multi-faceted content generation or information retrieval.

### Prompt Chaining

* **File:** `Prompt_Chaining_Langgraph.ipynb`
* **Concept:** Illustrates "Prompt Chaining," where the output of one LLM call serves as the input for the next, enabling sequential refinements or transformations of content.
* **Key Features:** Sequential LLM calls, iterative content refinement, conditional flow.
* **Use Case:** Multi-stage content refinement or complex reasoning.

### Routing

* **File:** `Routing_Langgraph.ipynb`
* **Concept:** Demonstrates dynamic "Routing," where an LLM analyzes input to decide which subsequent LLM call or tool to invoke, creating adaptive workflows.
* **Key Features:** LLM-driven decision-making for workflow paths, structured output for explicit routing.
* **Use Case:** Building flexible chatbots or multi-purpose agents.

### Evaluator-Optimizer

* **File:** `Evaluator_optimizer.ipynb`
* **Concept:** Showcases the "Evaluator-Optimizer" pattern, a feedback loop where one LLM generates content and another evaluates it, providing feedback for iterative refinement.
* **Key Features:** LLM feedback loop, structured output for evaluation, conditional loops for refinement.
* **Use Case:** Automated content generation with quality control or self-correction.

### Human-in-the-Loop

* **File:** `humanintheloop_langgraph.ipynb`
* **Concept:** Demonstrates integrating "Human-in-the-Loop" (HITL) functionality, allowing the workflow to pause for human input or decisions and then resume.
* **Key Features:** Manual state updates for human input, conditional routing based on human/LLM decisions.
* **Use Case:** Interactive assistants, approval workflows, or data annotation tasks.

---

## 3. Setup and Installation

To run these notebooks, you'll need to set up your Python environment and install the necessary libraries.

1.  **Clone the repository (if applicable):**
    ```bash
    git clone https://github.com/Abubakar0011/LangGraph_Different_workflows.git
    cd https://github.com/Abubakar0011/LangGraph_Different_workflows.git
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate # On Windows: .\venv\Scripts\activate
    ```

3.  **Install dependencies:**
    The notebooks primarily use `langchain`, `langgraph`, `pydantic`, and `python-dotenv`.
    You will also need an LLM provider. The notebooks use `langchain-groq` and `langchain-openai`.

    ```bash
    pip install langchain langchain-groq langgraph pydantic python-dotenv jupyter ipykernel
    # If using OpenAI:
    # pip install langchain-openai
    ```

4.  **Set up API Keys:**
    These notebooks require API keys for Large Language Models (LLMs).

    * Create a `.env` file in the root directory of your project.
    * Add your API keys to this file. For example:
        ```
        GROQ_API_KEY="your_groq_api_key_here"
        OPENAI_API_KEY="your_openai_api_key_here" # If using OpenAI
        ```
    * Ensure `load_dotenv()` is called in your notebooks (it's present in the provided files).

---

## 4. Usage

1.  **Start Jupyter Notebook:**
    ```bash
    jupyter notebook
    ```
2.  **Navigate:** Open the desired `.ipynb` file in your browser.
3.  **Run Cells:** Execute the cells sequentially to understand the flow and see the patterns in action.
    * **Important:** Ensure your LLM is correctly initialized (e.g., `llm = ChatGroq(model="qwen-qwq-32b")`) at the beginning of each notebook or in a shared setup file. The provided notebooks include placeholder `llm` initialization which you should replace with your actual LLM client.

---

## 5. Contributing

Contributions are welcome! If you have new LangGraph patterns to demonstrate or improvements to existing ones, feel free to open an issue or submit a pull request.

---