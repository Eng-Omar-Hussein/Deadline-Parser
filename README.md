# Deadline-Parser
# Flan-T5 Task & Deadline Extractor

A robust NLP-powered API that extracts structured tasks and deadlines from unstructured text. This project utilizes a fine-tuned **Google Flan-T5-Base** model, specifically trained to handle complex professional and informal communication.

## 🚀 The Feature
The core feature of this repository is a deep-learning inference engine that transforms messy, natural language emails or chat messages into clean Task/Deadline pairs.

### What makes this model special?
Unlike simple keyword search or regex-based systems, this model understands **context**:
* **Linguistic Flexibility:** It handles professional business English, tech-heavy jargon (e.g., "distillation models," "Expo router"), and multi-lingual slang (e.g., Egyptian Arabic phrases).
* **Relative Time Recognition:** It can identify deadlines like "Friday at 3:00 PM," "EOD," "tomorrow morning," or "October 15th."
* **Noise Filtering:** It distinguishes between actionable tasks and general conversation.

## 🧠 The Model
The underlying model is a Seq2Seq (Sequence-to-Sequence) Transformer based on **Flan-T5**. 

* **Base Model:** `google/flan-t5-base`
* **Task:** Token Classification & Text Generation
* **Training Focus:** Fine-tuned on a custom dataset of business emails and technical project management communications to recognize the specific relationship between an action (Task) and its constraint (Deadline).

### 🛠 Setup & Installation
1. Download Model Weights
Due to file size constraints, the model weights are hosted on Google Drive.

Download Link: Model link 


Instructions: Download and extract the folder, rename it to final_extraction_model, and place it in the root directory.
#### Install Requirements

pip install fastapi uvicorn transformers torch

### Run the Service

python main.py  

### API Output

Input: "The presentation for the graduation project is on Sunday morning."

Output: "extraction": "Task: submit quarterly financial review | Deadline: Friday at 3:00 PM"
