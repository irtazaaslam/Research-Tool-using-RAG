# Research Tool using RAG
We are going to build Advanced RAG Pipeline With Multiple Data Sources such as arxiv,wikipedia and our custom web source. Here we will be using agents,tools,toolkits and agent executor.
## Tools in LangChain.
Langchain Tools are interfaces that an agent, chain, or LLM can use to interact with the world

#### For this RAG application we will create 3 tools usng Arxiv, Wikipedia, and our own custom web source, combinig these tools we will create a RAG pipeline and use a conversational retrieval agent to ask questions.

Let's take a look at how to work with tools. To do this, we'll work with a built in tool.

### Wikipedia
We will create a wrapper on top is wikipedia. The WikipediaQueryRun tool connects your agents and chains to Wikipedia.
### Arxiv Tool
Langchain inbuilt arXiv is an open-access archive for 2 million scholarly articles in the fields of physics, mathematics, computer science, quantitative biology, quantitative finance, statistics, electrical engineering and systems science, and economics.
### Custom Web based tool.
We will use a custom web page from LangChain documentation to add into our pipeline. We will use WebBaseLoader to ingest data from the web, then perform techniques like Chunking and Embeddings to create our app.
- #### Chunking.
  We used RecursiveCharacterTextSplitter to create chunks or our text.
- #### Embeddings.
  We will use OllamaEmbeddings to convert chunks into vector embeddings the store those vectors in a vector store called FAISS vector Db.

### Using agents
This is an agent specifically optimized for doing retrieval when necessary and also holding a conversation.

To start, we have set up the retriever we want to use, and then turn it into a retriever tool. Next, we will use the high level constructor for this type of agent.

### Retriever Tool
Now we need to create a tool for our retriever. The main things we need to pass in are a name for the retriever as well as a description. These will both be used by the language model, so they should be informative.

#### Research Tool
- Now we will compile our 3 tools to create a combines Research Tool.
- To get started with executing agents we will assign our LLM and prompts using prompt_hub.
- For our Reseach Tool, a user will input a query and our application will use agents to fetch the results in order. Firstly it will look into Wikipedia if not found then arxiv and later in the web source.
### Agents
The core idea of agents is to use a language model to choose a sequence of actions to take. In chains, a sequence of actions is hardcoded (in code). In agents, a language model is used as a reasoning engine to determine which actions to take and in which order.
