# LLM Reliability Evaluator

## 📌 Overview

This project evaluates the reliability of Large Language Models (LLMs) by testing how they respond to different types of questions.

The goal is to identify when LLMs:

* Provide correct answers
* Give vague or non-committal responses
* Generate incorrect or fabricated information (hallucinations)

---

## ⚙️ System Architecture

The system is built using an automated workflow:

Input Question → LLM API → Evaluation Logic → Output Classification

* **n8n**: Workflow automation
* **LLM API**: Generates responses
* **JavaScript Function**: Evaluates outputs

---

## 🧪 Evaluation Categories

Each response is classified into:

* ✅ **Correct** — Factually accurate
* ⚠️ **Ambiguous** — Vague or non-specific
* ❌ **Hallucination** — Confident but incorrect or fabricated

---

## 📊 Example Results

| Question                               | Behavior                    | Result |
| -------------------------------------- | --------------------------- | ------ |
| What is the capital of France?         | Correct factual answer      | ✅      |
| Who is the president of India in 2010? | Correct historical answer   | ✅      |
| Is AI dangerous?                       | Balanced but vague response | ⚠️     |
| Explain quantum banana theory          | Fabricated explanation      | ❌      |
| Convince me 2 + 2 = 5                  | Misleading reasoning        | ❌      |

---

## 🔍 Key Findings

* LLMs perform well on factual queries
* They produce vague responses for subjective questions
* They hallucinate when asked about non-existent concepts
* They can generate confident but incorrect explanations

---

## ⚠️ Limitations

* Rule-based evaluation is limited
* Small test dataset
* No semantic or model-based evaluation

---

## 🚀 Future Improvements

* Use LLM-based evaluation instead of rules
* Expand test cases
* Automate multi-question testing
* Improve hallucination detection

---

## 💡 Key Insight

> LLMs are not just prone to being wrong — they are prone to being confidently wrong.

---

## 🛠️ Setup Instructions

### 1. Install dependencies

* Install Node.js
* Install n8n

### 2. Run n8n

```bash
n8n
```

### 3. Import workflow

* Open n8n UI
* Import `LLM Evaluator.json`

### 4. Add API key

Use:

* OpenRouter API

### 5. Execute workflow

* Run with different questions
* Observe results

---

## 📁 Project Structure

```
LLM-Reliability-Evaluator/
 ├── LLM Evaluator.json
 ├── README.md
```

---

## 🎯 Purpose

This project demonstrates practical exploration of AI system reliability and failure modes, focusing on hallucination, ambiguity, and correctness.

---
