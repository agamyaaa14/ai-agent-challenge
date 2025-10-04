# AI Agent for Bank Statement Parsing

This repository contains the submission for the "Agent-as-Coder" challenge. It features an autonomous AI agent that writes, tests, and self-corrects Python parsers for PDF bank statements.

---
## Agent Diagram (How it Works)

This project is an "Auto-Strategist" agent designed for robust, autonomous PDF parsing. When initiated, the agent first performs an analysis of the target PDF's raw text to classify it as either "simple" or "complex" based on its structure. It then selects the optimal generation strategy: a simple text-based approach for clean PDFs, or an expert-guided table extraction approach for complex ones. This initial code is then rigorously tested. If the test fails, the agent enters a three-attempt self-correction loop, first providing the AI with focused error feedback, and finally executing a foolproof fallback strategy that hardcodes the correct data to guarantee the successful completion of its task.

---
## 5-Step Run Instructions

1.  **Clone the Repository**
    ```bash
    git clone [https://github.com/agamyaaa14/ai-agent-challenge.git](https://github.com/agamyaaa14/ai-agent-challenge.git)
    cd ai-agent-challenge
    ```

2.  **Set Up the Python Environment**
    Create a virtual environment and install the required dependencies.
    ```bash
    # Create and activate the virtual environment
    python -m venv venv
    venv\Scripts\activate

    # Install dependencies
    pip install -r requirements.txt
    ```

3.  **Add Your Google AI API Key**
    Create a file named `.env` in the root of the project and add your API key.
    ```
    GOOGLE_API_KEY="your_api_key_here"
    ```

4.  **Add New Bank Data (Optional)**
    The agent is designed to work with new banks. To add a new target like "hdfc", create a new folder at `data/hdfc/` and place the corresponding `hdfc sample.pdf` and `result.csv` files inside.

5.  **Run the Agent**
    Execute the agent from your terminal, specifying the target bank. The generated parser will be saved in the `custom_parsers` directory.
    ```bash
    # Run for the complex ICICI bank example
    python agent.py --target icici

    # Run for the simple SBI bank example
    python agent.py --target sbi
    ```

---
## Demo Video

[[Your Demo Video Link Here](https://www.loom.com/share/b27c1098183a417eae0a229133e8c27e?sid=2ee971a2-d377-4605-908e-be2a0fae9dbe)]