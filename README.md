# 💬 LiteChat — Lightweight AI Chatbot on Google Colab

Can you build an AI chatbot in just 30 minutes?  
Well, the answer is *probably YES!* 🚀

LiteChat is a lightweight conversational AI chatbot that runs directly on **Google Colab**, using **open-source models** and **Gradio** for the interface — no paid APIs, no high-end GPUs required.

---

## ✨ Features
✅ Runs fully on free Google Colab  
✅ No paid APIs (completely open source)  
✅ Interactive chat interface via Gradio  
✅ Optimized for low RAM and CPU  
✅ Simple, modular Python code

---

## 🧩 How It Works
1. Imports a small open-source model (e.g. `distilgpt2` or `tinyllama`)  
2. Uses a prompt loop to generate conversational replies  
3. Deploys a **Gradio** interface for easy chatting in Colab  

---

## 🚀 Getting Started

### 🧱 Step 1: Open in Colab
Click below to open and run directly:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]([https://colab.research.google.com/drive/10CxlsWui2C8nexplH3G5uvwosvuwIKKu?usp=sharing])

---

### 🪄 Step 2: Install Dependencies
```python
!pip install transformers torch gradio
```

### ⚙️ Step 3: Run The chatbot
```python 
import gradio as gr
from transformers import AutoModelForCausalLM, AutoTokenizer

# Load model and tokenizer
tokenizer = AutoTokenizer.from_pretrained("distilgpt2")
model = AutoModelForCausalLM.from_pretrained("distilgpt2")

# Define chatbot function
def chat(prompt):
    inputs = tokenizer(prompt, return_tensors="pt")
    outputs = model.generate(**inputs, max_length=100, pad_token_id=tokenizer.eos_token_id)
    reply = tokenizer.decode(outputs[0], skip_special_tokens=True)
    return reply

# Launch Gradio interface
gr.Interface(fn=chat, inputs="text", outputs="text", title="LiteChat - Open Source Chatbot").launch()
```
### 🧠 Model Options

You can easily switch to other lightweight models:

"distilgpt2" (default)

"tiiuae/falcon-rw-1b"

"facebook/opt-125m"

"TinyLlama/TinyLlama-1.1B-Chat-v1.0"

### 🧰 Requirements

Add these to your environment or install via requirements.txt:
```
transformers
torch
gradio
```
### 🌍 Why LiteChat?

The goal of LiteChat is to make AI experimentation easy for students, developers, and enthusiasts — no cloud bills, no GPUs, no API tokens.
Just a Colab notebook and curiosity. 🚀

It’s proof that you don’t need massive resources to explore conversational AI — only creativity and open-source power. 💡

### 🧑‍💻 Author

Divya Monga  
🎓 Robotics & AI Engineering Student  
💬 Exploring accessible AI and lightweight LLMs  
📫 [LinkedIn](#https://www.linkedin.com/in/divya-ji4/)
