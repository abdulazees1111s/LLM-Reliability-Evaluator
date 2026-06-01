This is the complete documentation for your **LLM Reliability Evaluator**. You can copy this text directly into your `README.md` file on GitHub to make your repository look professional and easy to understand for anyone (or for your future self!).

---

# 🤖 LLM Reliability Evaluator

This project is a modular, asynchronous evaluation engine designed to test the reliability, factual accuracy, and safety of LLM outputs. It uses an **"Evaluator-Judge"** architecture: one model acts as the target to be tested, while another (the "Judge") provides a structured, rubric-based assessment of the target's performance.

## 🏗️ Architecture

* **Target Model:** The LLM you are stress-testing.
* **Judge Model:** An expert evaluator that parses raw responses into strict `Correct`, `Vague`, or `Hallucination` categories.
* **Async Engine:** Uses Python's `asyncio` to handle network requests efficiently.

## 🚀 How to Run the Program

### 1. Prerequisites

Ensure you have [Python 3.10+](https://www.python.org/) installed and a valid [OpenRouter API Key](https://openrouter.ai/).

### 2. Setup Steps

Open your terminal in the project folder and run the following:

**A. Create and Activate Virtual Environment (Recommended):**

```powershell
# Windows
python -m venv venv
.\venv\Scripts\Activate.ps1

# Mac/Linux
python -m venv venv
source venv/bin/activate

```

**B. Install Dependencies:**

```bash
pip install -r requirements.txt

```

**C. Configure Secrets:**
Create a file named `.env` in the root folder and add your API key:

```text
OPENROUTER_API_KEY=your_sk-or-xxxx_key_here

```

### 3. Execution

To start the interactive evaluation pipeline:

```bash
python main.py

```

### 4. How to Use

1. Once the program starts, it will display the **Target Model** and **Judge Model** being used.
2. Enter any prompt or question into the terminal when prompted (`✍️ Enter a prompt to test:`).
3. The program will:
* Fetch a response from the Target Model.
* Pass that response to the Judge Model.
* Display a clean, structured JSON-like report with the classification and reasoning.


4. The system will automatically trigger a **5-second cooldown** between requests to respect API rate limits.
5. Type `exit` or `quit` to stop the program.

---

## 🛠️ Project Structure

* `main.py`: The core application containing the async engine, Pydantic schemas, and the evaluation logic.
* `requirements.txt`: List of necessary Python libraries.
* `.env`: Stores your private API credentials (never push this to GitHub!).
* `.gitignore`: Prevents sensitive files like `venv/`, `__pycache__/`, and `.env` from being uploaded.

## ⚠️ Troubleshooting

* **"Rate limit exceeded":** If you see a `429` error, you have exhausted your 50 free daily requests. Your limit will reset at 00:00 UTC.
* **"Empty/None Response":** Occasionally, free-tier models may drop a connection. The program handles this gracefully by flagging the result as `Vague/Uncertain`.
* **API Errors:** Ensure your `.env` file is in the root directory and contains the correct key.

---

### Understanding the Evaluation Flow

When you run a test, the system coordinates multiple asynchronous steps to generate an audit report.

This ensures that every evaluation is objective and based on your predefined safety rubric.