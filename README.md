# Deadline-Parser: Flan-T5 Task & Deadline Extractor

A robust NLP-powered API that extracts structured tasks and deadlines from unstructured text. This project utilizes a fine-tuned **Google Flan-T5-Base** model, specifically trained to handle complex professional and informal communication.

## 🚀 Key Features
The core feature of this repository is a deep-learning inference engine that transforms messy, natural language emails or chat messages into clean Task/Deadline pairs.

* **Linguistic Flexibility:** Handles professional English, tech jargon (e.g., "distillation models," "Expo router"), and informal context.
* **Relative Time Recognition:** Identifies deadlines like "Friday at 5pm," "EOD," "tomorrow morning," or specific dates.
* **Noise Filtering:** Distinguishes between actionable tasks and general conversation.

## 🧠 The Model
The underlying engine is a Seq2Seq (Sequence-to-Sequence) Transformer based on **Flan-T5**. 

* **Base Model:** `google/flan-t5-base`
* **Architecture:** Encoder-Decoder Transformer
* **Training Focus:** Fine-tuned on a custom dataset of business emails and project management communications.

## 📊 Extraction Examples (Test Results)
The following table demonstrates the model's actual performance on real-world inputs:

| Input Email/Text | Model Output (Raw Result) |
| :--- | :--- |
| "Please submit the financial report by next Friday at 5pm." | `Task: Submit financial report \| Deadline: next Friday at 5pm` |
| "We need to finish the slide deck for the client presentation by Tuesday morning." | `Task: Finish slide deck \| Deadline: Tuesday morning` |
| "The server migration must be completed before the system downtime starts at 11 PM tonight." | `Task: Complete server migration \| Deadline: at 11 PM tonight` |

## 🛠 Setup & Installation

### 1. Download Model Weights
Due to file size constraints, the model weights are hosted externally.
* **Download Link:** [Model link here]
* **Instructions:** Download and extract the folder, rename it to `final_extraction_model`, and place it in the root directory.

### 2. Install Requirements
```bash
pip install fastapi uvicorn transformers torch
