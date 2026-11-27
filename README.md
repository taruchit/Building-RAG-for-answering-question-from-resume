# Building-RAG-for-answering-question-from-resume

**Project overview**

Here we have built a RAG application which parses my resume to enable hiring managers seeking details from it without going through all the content manually. It helps to evaluate the profile against the required skillsets and determine if any supporting information is found related to it.

**Problem statement**

Resume is a highly customized document which is regularly updated with details such as years of experience, skillsets, organizations worked for, courses & certifications and open-source projects. Moreover, the format and template of resume may also change over the period of time. 
Thus, it felt important to have an application that provides information specific to the current profile and leverage it to fill the gaps. 

**Motivation to solve the problem**

It gives me an opportunity to evaluate my own resume based on the skillsets and role requirements listed in job description to understand if I have covered relevant details for the hiring manager.

**High-level details to parse the PDF file**

1. Loading the PDF file using PyPDFLoader.
2. Defining the text splitter's configurations using RecursiveCharacterTextSplitter.
3. Splitting the document into smaller chunks as per the text splitter using split_documents.
4. Storing embedding of the chunks in Chroma DB vector store.
5. Then we create a VectoreStoreRetriever from vector store so that we can query the document.
6. We define RAG pipeline to handle the input and fetch results via LLM based on the data fetched from the document.
7. Finally we define the question and fetch the corresponding response.

**Configurations**

1. Document loader: PyPDFLoader
2. Embedding: OpenAI Embedding -> text-embedding-3-small
3. LLM model: OpenAI -> gpt-4o-mini
4. Temperature: 0 (Deterministic results)
5. Chunk size: 1000
6. Chunk overlap: 200

