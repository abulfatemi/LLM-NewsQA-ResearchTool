# LLM-NewsQA-ResearchTool

This project provides a streamlined interface for users to input URLs of news articles, process the content, and ask questions about the articles. It leverages advanced language models to generate accurate answers and cite sources. Designed for journalists, researchers, and anyone interested in extracting insights from news content, this tool simplifies information retrieval and analysis.


## Project Working

- Users input up to three URLs of news articles in the Streamlit app and click the "Process URLs" button. The app fetches the content from these URLs using the UnstructuredURLLoader.

- The fetched content is split into smaller chunks using the RecursiveCharacterTextSplitter, ensuring efficient processing. These chunks are then converted into numerical vectors (embeddings) using a pre-trained model (sentence-transformers/all-MiniLM-L6-v2) from the Hugging Face library.
- The embeddings are stored in a FAISS index, which allows for quick and efficient similarity searches. The FAISS index is saved to a file (faiss_store.pkl) for future use.
- Users can enter a question in the app's text input field. The app uses the RetrievalQAWithSourcesChain model, powered by Google's Generative AI, to retrieve relevant information from the FAISS index and generate an answer.
- The answer, along with its sources (if available), is displayed in the app's interface, providing users with accurate and relevant information based on the news articles they provided.


## News article URLs used
- https://www.thehindu.com/news/national/kerala/wayanad-landslides-live-updates-august-1/article68471570.ece
- https://www.livemint.com/news/hamas-chief-ismail-haniyeh-shared-stage-with-nitin-gadkari-hours-before-he-was-killed-in-iran-11722430281887.html
- https://www.ndtv.com/india-news/shimla-cloudburst-himachal-cloudburst-uttarakhand-cloudburst-20-missing-after-cloudburst-in-shimla-monsoon-fury-in-uttarakhand-too-6236457

## Screenshot


![llm_news_articles](https://github.com/user-attachments/assets/5a454f8c-7dab-485b-94c6-abb5584a03bb)

