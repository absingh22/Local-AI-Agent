# Local-AI-Agent

This project implements a local AI agent that answers questions about a pizza restaurant. It utilizes Retrieval Augmented Generation (RAG) to provide contextually relevant answers by first retrieving pertinent information from a database of restaurant reviews.

## Features

* **Local LLM Integration:** Uses Ollama (`llama3.2` by default) for running the language model locally.
* **Retrieval Augmented Generation (RAG):** Enhances answers by retrieving relevant restaurant reviews from a vector database.
* **Chroma Vector Store:** Employs `langchain-chroma` for efficient storage and retrieval of document embeddings.
* **Realistic Review Data:** Populated with restaurant reviews from `realistic_restaurant_reviews.csv`.
* **Interactive Q&A:** Provides a simple command-line interface to ask questions about the restaurant.

## Project Structure

* `main.py`: The main application script that sets up the LLM, prompt, and RAG chain, and handles user interaction.
* `vector.py`: Manages the creation and persistence of the Chroma vector database from the restaurant reviews.
* `realistic_restaurant_reviews.csv`: A dataset of simulated restaurant reviews used to populate the vector store.
* `requirements.txt`: Lists the Python dependencies required to run the project.

## Setup and Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/absingh22/Local-AI-Agent](https://github.com/absingh22/Local-AI-Agent)
    cd LocalAIAgentWithRAG
    ```

2.  **Install Ollama:**
    Follow the instructions on the [Ollama website](https://ollama.com/download) to install Ollama for your operating system.

3.  **Pull the Llama 3.2 model (or your preferred model):**
    ```bash
    ollama pull llama3.2
    ```
    *Note: The `main.py` script is configured to use `llama3.2`. If you pull a different model, update the `model` variable in `main.py` accordingly.*

4.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

5.  **Install Python dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

6.  **Initialize the Vector Database:**
    Run `vector.py` once to create and populate the Chroma vector store. This will create a directory named `chrome_langchain_db`.
    ```bash
    python vector.py
    ```

## Usage

After completing the setup, you can run the main application:

```bash
python main.py
