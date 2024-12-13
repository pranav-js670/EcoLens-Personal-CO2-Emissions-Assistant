# EcoLens: Personal CO2 Emissions Assistant

EcoLens is an AI-powered application that helps users analyze their daily activities, calculate their carbon footprint, and offers actionable suggestions to reduce emissions. Built with advanced AI technologies, EcoLens enables users to make data-driven decisions for a more sustainable lifestyle.

---

## Table of Contents
- [Features](#features)
- [Technologies Used](#technologies-used)
- [How It Works](#how-it-works)
- [Installation and Setup](#installation-and-setup)
- [Project Workflow](#project-workflow)
- [Contributing](#contributing)
- [License](#license)

---

## Features
- Analyze daily activities to estimate carbon emissions.
- Receive personalized and actionable strategies to reduce emissions.
- Interactive user interface built with Streamlit.
- Utilizes Retrieval-Augmented Generation (RAG) for accurate and context-aware responses.
- Efficient vector search powered by FAISS.
- Open-source **Llama3-8B** model inference through Groq API.

---

## Technologies Used
- **Streamlit**: For building the interactive user interface.
- **LangChain**: To enable Retrieval-Augmented Generation (RAG) for accurate answers.
- **FAISS**: Facebook AI Similarity Search for vector-based retrieval.
- **HuggingFace Embeddings**: For generating vector embeddings of text data.
- **Groq API**: An inference engine for the open-source **Llama3-8B** model by Meta.

---

## How It Works
1. **User Input**:
   - Users enter their daily activities or consumption patterns.
   - Users also input questions related to reducing their CO2 emissions.

2. **Text Preprocessing**:
   - The context (user activities) is split into smaller chunks using the `CharacterTextSplitter` from LangChain.

3. **Embedding Generation**:
   - Context chunks are converted into vector embeddings using **HuggingFace Embeddings**.

4. **Vector Indexing**:
   - The embeddings are stored in the FAISS vector store for efficient similarity search.

5. **Query Processing**:
   - The user's question is converted into a vector embedding (on the fly) and matched with stored embeddings in the FAISS vector store to retrieve the most relevant chunks.

6. **Answer Generation**:
   - The relevant context and question are passed to the **Llama3-8B** model (via the Groq API) to generate insightful, context-aware responses.

7. **Interactive Output**:
   - The generated answer is displayed on the Streamlit interface for the user.

---

## Installation and Setup

### Prerequisites
- Python 3.8 or above
- Groq API Key
- Necessary Python libraries (listed in `requirements.txt`)

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/pranav-js670/EcoLens-Personal-CO2-Emissions-Assistant.git
   cd EcoLens
   ```

2. Add your Groq API key: Replace GROQ_API_KEY in the code with your actual API key

3. Run the application:
   ```bash
   streamlit run main.py
   ```

## Project Workflow

### 1. Data Collection:
- Users provide their daily activity details and specific questions.

### 2. Vectorization:
- The provided context is transformed into vector embeddings using **HuggingFace Embeddings**.

### 3. Storage and Retrieval:
- Embeddings are stored in **FAISS**. On a question query, relevant context is retrieved via similarity search.

### 4. RAG Process:
- The question and retrieved context are combined to form a prompt, which is sent to the **Llama3-8B** model via the **Groq API** for inference.

### 5. Response Generation:
- The model generates an insightful, context-aware answer which is presented to the user.

## Contributing
Contributions are welcome! Please fork the repository, make your changes, and submit a pull request. Ensure all new features are well-documented and tested.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

