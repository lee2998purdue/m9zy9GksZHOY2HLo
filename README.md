# Apziva Project 3: Potential Talents

## Project Overview
This project implements an intelligent talent acquisition pipeline that ranks job candidates based on how their job profiles match specific search terms. By evolving from basic statistical models to state-of-the-art Large Language Models (LLMs) and Agentic workflows, the system provides both high accuracy and human-like interpretability for recruiters.

## Files
### Exploratory Data Analysis
- EDA.ipynb
### Candidate Ranking
- Modeling.ipynb 


## Conclusion
### Exploratory Data Analysis
This project analyzed a dataset of job candidates to identify key patterns in job titles, locations, and network counts. The findings reveal a high concentration of aspiring HR professionals and university students primarily located in Canada, Texas, and New York, with a significant portion of the talent pool maintaining 500+ professional connections. Geographical hotspots showed distinct professional profiles, notably with Houston and North Carolina serving as major hubs for human resources specialists and business graduates.

### Candidate Ranking
Throughout this project, I explored a spectrum of candidate-ranking methodologies, ranging from statistical approaches to state-of-the-art Large Language Models (LLMs). 

- **TF-IDF Vectorization** I began with TF-IDF, which demonstrated how word frequency and uniqueness within a corpus can be used to determine relevance. While effective for keyword matching, it lacked a deeper semantic understanding.
- **Word Embeddings** Using word embeddings (Word2Vec, GloVe, FastText), I mathematically calculated semantic similarities by tokenizing the corpus and mapping each token to its corresponding vector space representation. This stage addressed the 'Out-of-Vocabulary' (OOV) limitation, identifying how unseen words could lead to errors.
- **Large Language Models (LLMs)** Delegating the ranking task to LLMs (like Qwen and GLM) provided a significant improvement in performance and interpretability. The models provided high-quality reasoning for each ranking decision, moving the system closer to human-like evaluation. Using Ollama locally allowed for optimized inference.
- **Fine-Tuning** To adapt the models to specific talent acquisition datasets, I utilized QLoRA for parameter-efficient fine-tuning. This process improved the model's ability to handle job titles outside the original training set, though it introduced considerations regarding model storage and deployment overhead.
- **Retrieval-Augmented Generation (RAG)** I implemented a RAG pipeline leveraging FAISS to dynamically retrieve and inject relevant candidate profiles into the model's context during inference. This architecture provides a highly scalable solution, enabling the system to rank new, unseen data in real-time without the need for additional model training.
- **Gemini Integration & Agentic Workflows** Finally, I explored the Gemini API to develop a dedicated Talent Matcher App. Despite free-tier rate limits, the app successfully showcased agentic workflows using LangGraph. The system intelligently detected geographical intent in search terms, automatically calling relevant tools to calculate location-based proximity.
