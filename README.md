# treehacks-2024
View InterSystem's challenge [here](/TREEHACKS_CHALLENGE.md)
## InterSystems IRIS Vector Search Quickstart


1. Clone the repo
    ```
    https://github.com/alvin-isc/treehacks-2024.git
    ```
    In the following steps, replace 'PATH-TO-REPO' with the path to the repo. 
2. Install IRIS (Community Edtion) in a container:
    ```
    docker run -d --name iris-comm \
    -p 1972:1972 \
    -p 52773:52773 \
    intersystemsdc/iris-community:2024.1-preview
    ```
    - Access the System Management Portal via http://localhost:52773/csp/sys/UtilHome.csp (user: SUPERUSER, pw: SYS)
    - Change the password as prompted. The demo notebooks use a password of 'SYS2'.
3. Create a python environment (conda, venv or however you wish) For example:
    
    ```
    conda create --name treehacks-iris python=3.10
    ``` 

4. Install packages for all demos:
    ```
    pip install -r requirements.txt
    ```

5. For [langchain_demo.ipynb](demo/langchain_demo.ipynb) and [llama_demo.ipynb](demo/llama_demo.ipynb) , you need an [OpenAI API Key](https://platform.openai.com/api-keys). Create a .env file in this repo to store the key:
    ```
    OPENAI_API_KEY=xxxxxxxxx
    ```
    
## Basic Demos

### [sql_demo.ipynb](demo/sql_demo.ipynb)
IRIS SQL now supports vector search (with filters)! In this demo, we're searching a whiskey dataset for whiskeys that are priced < $100 and have a taste description similar to "earthy and creamy taste".

### [langchain_demo.ipynb](demo/langchain_demo.ipynb)
IRIS now has a langchain integration as a VectorDB! In this demo, we use the langchain framework with IRIS to ingest and search through a document. 

### [llama_demo.ipynb](demo/llama_demo.ipynb)
IRIS now has a llama_index integration as a VectorDB! In this demo, we use the llama_index framework with IRIS to ingest and search through a document. 

## Which to use?
If you need to use hybrid search (similarity search with filters), use IRIS SQL. 

If you're building a genAI app that uses a variety of tools (agents, chained reasoning, api calls), go for langchain. 

If you're building a RAG app, go for llama_indx.

Feel free to contact Alvin / Thomas if you have any questions!

## More Demos / References:

### [NLP Queries on  Youtube Audtio Transcription](https://github.com/jrpereirajr/intersystems-iris-notebooks/blob/main/vector/langchain-iris/nlp_queries_on_youtube_audio_transcription_dataset.ipynb)
Uses langchain-iris to search Youtube Audiot transcriptions

### [langchain-iris demo](https://github.com/caretdev/langchain-iris/blob/main/demo.ipynb)
Original IRIS langhain demo, that runs the containerized IRIS in the notebook

### [llama-iris demo](https://github.com/caretdev/llama-iris/blob/main/demo.ipynb)
Original IRIS llama_index demo, that runs the containerized IRIS in the notebook

### [InterSystems Documentation](https://docs.intersystems.com/)
Official page for InterSystems Documentation
