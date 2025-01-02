# corrective_rag_antropic_openai
# Corrective RAG Agent

## Overview
This project implements a Corrective Retrieval-Augmented Generation (RAG) Agent that enhances the user query process by utilizing LangChain, Anthropic's Claude, OpenAI, and other powerful AI tools. The agent integrates capabilities like document ingestion, query transformation, retrieval from vectorstores, relevance grading, and dynamic response generation.

## Key Features
- **Multi-step Workflow:** Utilizes a StateGraph for orchestrating multi-step processes like document retrieval, grading, web search, and response generation.
- **Dynamic Document Input:** Accepts input from URLs and uploaded files (PDF, TXT, Markdown).
- **API Key Configuration:** Supports secure configuration for Anthropic, OpenAI, Qdrant, and Tavily APIs.
- **Advanced Vector Search:** Employs Qdrant for vector-based document retrieval.
- **Relevance Grading:** Filters irrelevant documents using Anthropic's Claude for better accuracy.
- **Web Search Integration:** Searches the web via Tavily API for context enrichment.

## Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/akshayram1/corrective_rag_antropic_openai
   cd corrective_rag_antropic_openai
   ```

2. **Set Up Python Environment**
   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows, use `venv\Scripts\activate`
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## Configuration

1. **API Keys Setup**
   Configure your API keys for the following services in the Streamlit app sidebar:
   - OpenAI API Key
   - Anthropic API Key
   - Tavily API Key
   - Qdrant URL and API Key

2. **Optional Environment Variables**
   Alternatively, you can define API keys as environment variables:
   ```bash
   export ANTHROPIC_API_KEY=your_key
   export OPENAI_API_KEY=your_key
   export TAVILY_API_KEY=your_key
   export QDRANT_URL=http://localhost:6333
   export QDRANT_API_KEY=your_key
   ```

## Usage

1. **Start the Application**
   ```bash
   streamlit run app.py
   ```

2. **Provide Inputs**
   - Choose the input method (URL or file upload).
   - Enter your question in the text box.

3. **View Workflow Steps**
   The app provides detailed outputs for each workflow step, including retrieval, relevance grading, query transformation, and response generation.

4. **Final Output**
   Review the final response under the "Final Generation" section.

## Workflow Steps

1. **Document Ingestion:**
   - Loads documents from URLs or uploaded files.
   - Splits documents into chunks for effective retrieval.

2. **Query Transformation:**
   - Optimizes user queries to improve retrieval and search results.

3. **Retrieval:**
   - Retrieves relevant documents using Qdrant vectorstore.

4. **Relevance Grading:**
   - Uses Anthropic's Claude to filter irrelevant documents.

5. **Web Search:**
   - Augments context by fetching search results via Tavily.

6. **Response Generation:**
   - Generates a well-formulated answer using Anthropic's Claude.

## Dependencies
- [LangChain](https://python.langchain.com/)
- [Streamlit](https://streamlit.io/)
- [Qdrant](https://qdrant.tech/)
- [Anthropic](https://www.anthropic.com/)
- [OpenAI](https://openai.com/)
- [Tavily](https://tavily.com/)
- [PyPDF](https://pypdf2.readthedocs.io/)



## Known Issues
- Performance might be affected by slow APIs or large documents.
- Dependency on API keys requires secure handling to avoid unauthorized access.

## Future Enhancements
- Implement multi-language support.
- Add more vectorstore backends.
- Extend to additional file formats for ingestion.

## License
[MIT License](LICENSE)

## Acknowledgments
Special thanks to LangChain, Anthropic, and Qdrant for their APIs and frameworks that power this project.
