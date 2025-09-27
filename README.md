# KrishiMitra (कृषिमित्र)

**AI-Powered Advisor for Farmers** — a multilingual voice + text assistant that provides hyper-local, data-grounded recommendations (weather, soil, fertilizer, market prices, government schemes).
KrishiMitra revolutionizes agriculture in rural India by providing farmers with intelligent, data-driven insights. 
Designed specifically for small-scale farmers, our platform bridges the digital divide by offering voice-based 
interactions, regional language support. From weather predictions to crop management,fertilizer recommendations to market prices, KrishiMitra serves as your trusted agricultural companion, helping increase productivity while reducing costs and environmental impact.


## Demo
- Demo video (prototype walkthrough): `https://www.youtube.com/watch?v=fc93mcKCyEc`
- Presentation link:  'https://drive.google.com/drive/folders/1YFopROIqWkKpjTTDxeKQANWYiaI3H5-1?usp=sharing'


## About
KrishiMitra answers farmers’ queries using a **RAG (Retrieval-Augmented Generation)** pipeline:
- **Input:** voice or text from the web UI  
- **STT:** Google Cloud Speech-to-Text (`STT.py`)  
- **Normalization / Translation:** GoogleTrans
- **Retrieval/Tools:** LangChain → ChromaDB vector store (indexed from `dataset/`)  
- **LLM:** open-source model (prototype: Gemini) to generate grounded answers  
- **Output:** translated text returned in UI

## Features
- Voice + text queries (Hindi + regional Indian languages)  
- RAG-backed answers from public datasets (weather, soil, fertilizer, market prices, government schemes)  
- ChromaDB vector store + LangChain agents for retrieval  
- Lightweight Flask web UI for simple interactions  
- Scripts to build the retrieval index and run inference

#### now Step for installing and running the code.

## step 1,  Install & run
# clone repo
git clone https://github.com/kg0505/KrishiMitra
cd krishimitra

## step 2, activate environment
conda create venv/

# install dependencies
pip install -r requirements.txt

## Build vector store
python retriever/build_vectorstore.py 
--output-dir ./vectorstore/chroma_db

# run app
python main.py

Open `http://localhost:5000` to access the UI.

## Environment variables

GEMINI_API_KEY=AIzaSyB8QaeX...
OPENWEATHERMAP_API_KEY=2234932f05d2d8...
LOCAL_PRICE_API=http://127.0.0.1...
GOOGLE_API_KEY=AIzaSyC...
GOOGLE_CSE_ID=a63e5...
GEMINI_API_KEY1=AIzaSy...
GOOGLE_APPLICATION_CREDENTIALS=D:\...
GEMINI_API_KEY3=AIzaSyC...



## Sample queries:

* What will be the weather in Bangalore for next 5 days?
* Recommend fertilizer dosage for wheat per hectare with soil pH = 6.2
* Show current mandi price of wheat in [district]



**Known limitations**
* Internet + API dependency
* Limited dialect coverage
* Dependent on dataset completeness
* Credentials must be kept private
