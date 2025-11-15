# Physician Notetaker - Medical NLP Pipeline

## 📌 Overview
This project implements an **AI-powered NLP pipeline** for medical transcription, summarization, sentiment analysis, and SOAP note generation from physician-patient conversations.

### ✨ Features:
- **Named Entity Recognition (NER):** Extracts key medical details (Symptoms, Diagnosis, Treatment, Prognosis).
- **Text Summarization:** Converts unstructured transcripts into structured medical reports.
- **Sentiment & Intent Analysis:** Detects patient emotions and intent (e.g., seeking reassurance).
- **SOAP Note Generation:** Automatically structures conversations into **Subjective, Objective, Assessment, and Plan (SOAP)** format.

---

## 🚀 Installation

### **1. Clone the Repository**
```bash
 git clone [https://github.com/your-repo/physician-notetaker.git](https://github.com/Dev-debasish-09/Summary_Creation.git)]
 cd physician-notetaker
```

### **2. Set Up a Virtual Environment (Optional but Recommended)**
```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

### **3. Install Dependencies**
```bash
pip install -r requirements.txt
```

---

## 📂 Project Structure
```
📁 physician-notetaker/
│── 📜 README.md              # Project Documentation
│── 📁 Health_NLP/                 # Helper functions (NER, Sentiment Analysis, etc.)
```

---

## 🔧 Usage

### **1. Run the NLP Pipeline**
```bash
python main.py --input data/sample_transcript.txt
```

### **2. Expected Output (JSON Format)**
```json
{
  "Patient_Name": "Janet Jones",
  "Symptoms": ["Neck pain", "Back pain", "Head impact"],
  "Diagnosis": "Whiplash injury",
  "Treatment": ["10 physiotherapy sessions", "Painkillers"],
  "Current_Status": "Occasional backache",
  "Prognosis": "Full recovery expected within six months"
}
```

---

## 📌 Model Details

### **1. Named Entity Recognition (NER)**
- Uses `spaCy` and `SciSpaCy` for extracting medical entities.
- Alternative: Fine-tune `BioBERT` for medical term extraction.

### **2. Summarization**
- Utilizes `BART` or `T5` transformers for converting transcripts into structured medical reports.
```
objective: The patient is seen by a doctor in the back of a waiting room. The doctor says, "Good morning, Ms.\n

Objective: Mr. Jones is the son of former U.S. President Harry S. Jones. Mr. Jones has been married to his wife, Barbara, for more than 40 years.\n

Assessment: Patient: Good morning, doctor. Doctor: How are you feeling today? Patient: I'm fine.\n Plan: "I\u2019m doing better, but I still have some discomfort now and then," he said.\n
```

### **3. Sentiment & Intent Analysis**
- Uses `DistilBERT` or `ClinicalBERT` to classify patient sentiment.
- Intent detection for patient concerns (e.g., reassurance-seeking, reporting symptoms).

### **4. SOAP Note Generation**
- Rule-based structuring + NLP techniques for extracting and organizing medical details.
  ```
  SOAP Notes:
    Subjective: The patient is seen by a doctor in the back of a waiting room. The doctor says, "Good morning, Ms.
    Objective: Mr. Jones is the son of former U.S. President Harry S. Jones. Mr. Jones has been married to his wife, Barbara, for more than 40 years.
    Assessment: Patient: Good morning, doctor. Doctor: How are you feeling today? Patient: I'm fine.
    Plan: "I’m doing better, but I still have some discomfort now and then," he said.
  ```
  

