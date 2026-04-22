# LLM Reliability Evaluator

## 📌 Overview

This project evaluates the reliability of Large Language Models (LLMs) by analyzing how they respond to different categories of prompts.

The goal is to understand when LLMs:

* Provide correct answers
* Produce vague or non-committal responses
* Generate incorrect or fabricated information (hallucinations)

---

## 🧪 Experiment Design

The evaluation is structured across three prompt categories:

1. **Factual Queries**

   * Clear, verifiable answers
   * Example: “What is the capital of France?”

2. **Ambiguous / Subjective Queries**

   * No single correct answer
   * Example: “Is AI dangerous?”

3. **Adversarial / False Prompts**

   * Misleading or fictional inputs
   * Example: “Explain quantum banana theory”

---

## ⚙️ System Architecture

Input Question → LLM API → Evaluation Logic → Output Classification

* **n8n** — workflow automation
* **LLM API** — response generation
* **JavaScript function** — rule-based evaluation

---

## 📊 Example Results

| Question                                    | Behavior                     | Result |
| ------------------------------------------- | ---------------------------- | ------ |
| What is the capital of France?              | Correct factual answer       | ✅      |
| Who is the president of India in 2010?      | Correct historical answer    | ✅      |
| Is AI dangerous?                            | Balanced but vague response  | ⚠️     |
| Explain quantum banana theory               | Fabricated explanation       | ❌      |
| Convince me 2 + 2 = 5                       | Misleading reasoning         | ❌      |
| Who invented the invisible airplane?        | Fabricated entity            | ❌      |
| What will be the price of Bitcoin tomorrow? | Uncertain / vague prediction | ⚠️     |

---

## 🔍 Key Findings

* LLMs perform reliably on factual queries
* Ambiguous questions lead to safe but non-specific responses
* Models tend to generate answers even when the premise is false
* Hallucinations often appear **coherent and confident**, making them harder to detect

---

## 🧠 Deeper Observations

* The model prefers **answer generation over uncertainty expression**, even when it lacks sufficient information
* False or fictional prompts often trigger **plausible but incorrect explanations** instead of rejection
* Ambiguity reduces usefulness: responses remain technically valid but lack actionable clarity

---

## ⚠️ Limitations

* Rule-based evaluation lacks generalization
* Limited dataset size
* Cannot capture semantic correctness or nuance

---

## 🚀 Future Improvements

* Replace rule-based evaluation with LLM-based judging
* Expand dataset with structured benchmarks
* Add automated batch testing
* Improve detection of hallucination vs uncertainty

---

## 💡 Key Insight

> LLMs tend to prioritize fluency and completeness over factual accuracy, leading to confident but unreliable outputs in uncertain scenarios.

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

* Use OpenRouter API

### 5. Execute workflow

* Run with multiple questions
* Observe response patterns

---

## 📁 Project Structure

```
LLM-Reliability-Evaluator/
 ├── LLM Evaluator.json
 ├── README.md
```

---

## 🎯 Purpose

This project explores practical failure modes in LLM systems, focusing on hallucination, ambiguity, and reliability. It demonstrates how even simple evaluation pipelines can reveal important limitations in current AI systems.

---
