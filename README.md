# 🌱 KrishiMitra (कृषिमित्र)  
**AI-Powered Advisor for Farmers** — A multilingual **voice + text assistant** that delivers hyper-local, data-driven agricultural recommendations (weather, soil, fertilizer, market prices, and government schemes).  

KrishiMitra is designed to empower **small-scale farmers in rural India** by bridging the digital divide through **voice-based interactions** and **regional language support**. From weather predictions to crop management, fertilizer advice to mandi prices, KrishiMitra serves as a **trusted digital companion**, helping farmers increase productivity while reducing costs and environmental impact.  

---

## 🎥 Demo  
- **Project Overview Video (Explanation of KrishiMitra):**  https://youtu.be/fc93mcKCyEc 
- **Prototype Walkthrough Video:** https://www.youtube.com/watch?v=fc93mcKCyEc
- **Presentation Link:** https://drive.google.com/drive/folders/1YFopROIqWkKpjTTDxeKQANWYiaI3H5-1?usp=sharing  

---

## 📖 About  
KrishiMitra answers farmers’ queries using a **Retrieval-Augmented Generation (RAG)** pipeline:  

1. **Input:** Voice or text query from the web UI  
2. **STT:** Speech-to-Text via Google Cloud (STT.py)  
3. **Normalization / Translation:** GoogleTrans  
4. **Retrieval / Tools:** LangChain + ChromaDB vector store (built from dataset/)  
5. **LLM:** Open-source model (prototype: Gemini) generates grounded answers  
6. **Output:** Translated response returned to the UI  

---

## ✨ Features  
- 🔊 Voice + text queries (supports Hindi + regional Indian languages)  
- 📚 RAG-backed answers using public datasets (weather, soil, fertilizer, market prices, government schemes)  
- 🗂️ ChromaDB + LangChain agents for intelligent retrieval  
- 🖥️ Lightweight Flask web UI for farmer-friendly interactions  
- ⚡ Retrieval index builder + inference pipeline scripts included  

---

## ⚙️ Installation & Running  

### Step 1: Clone the Repository  
git clone https://github.com/kg0505/KrishiMitra
cd KrishiMitra

### Step 2: Setup Environment
# create and activate environment
conda create -n krishimitra python=3.10
conda activate krishimitra

# install dependencies
pip install -r requirements.txt

### Step 3: Build Vector Store
python retriever/build_vectorstore.py --output-dir ./vectorstore/chroma_db

### Step 4: Run the App
python main.py

### Environment Variables

# Set the following environment variables in a .env file or export them before running:

GEMINI_API_KEY=your_key_here
GEMINI_API_KEY1=your_key_here
GEMINI_API_KEY3=your_key_here
OPENWEATHERMAP_API_KEY=your_key_here
LOCAL_PRICE_API=http://127.0.0.1...
GOOGLE_API_KEY=your_key_here
GOOGLE_CSE_ID=your_id_here
GOOGLE_APPLICATION_CREDENTIALS=path/to/credentials.json


### Sample Queries

“What will be the weather in Bangalore for the next 5 days?”
“Recommend fertilizer dosage for wheat per hectare with soil pH = 6.2”
“Show current mandi price of wheat in [district]”


### Known Limitations

Requires Internet + external API access
Limited dialect coverage for some regional languages
Dependent on dataset completeness
Credentials must be kept private


### 🤝 Credits

This project was collaboratively developed with [Vardhman](https://github.com/vardhman916/KrishiMitra).  
Special thanks for contributions in design, development, and testing.
