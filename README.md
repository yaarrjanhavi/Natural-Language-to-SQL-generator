# NL-to-SQL Generator using Gemini 2.0 Flash

## Project Overview
This repository contains a Python-based pipeline that abstracts SQL complexity for non-technical users. By leveraging Large Language Models (LLMs), the system translates natural language questions into valid SQLite queries, executes them against a local database, and returns formatted results via Pandas.



## Key Features
* **Natural Language Translation:** Converts descriptive English into complex SQL (Aggregations, Joins, and Subqueries).
* **Prompt Engineering:** Utilizes System Role-playing and Few-Shot prompting to maintain SQLite-specific syntax.
* **Structured Output:** Enforces JSON response formats for programmatic status tracking (Success/Clarification/Error).
* **Data Visualization:** Automatically renders query results into tabular formats using Pandas.

## Technical Stack
* **LLM:** Google Gemini 2.0 Flash
* **Language:** Python 3.x
* **Database:** SQLite3
* **Libraries:** `google-genai`, `pandas`, `sqlite3`

## System Logic & Pipeline
1.  **Metadata Injection:** The database schema (DDL) is injected into the model's context window.
2.  **Inference:** The user's query is processed through a refined System Prompt.
3.  **Sanitization:** The output is parsed to extract clean SQL from the JSON response.
4.  **Execution:** The query is dispatched to the SQLite engine.
5.  **Post-Processing:** Result sets are converted into DataFrames for display.

## How to Run
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/NL-to-SQL-Generator.git](https://github.com/your-username/NL-to-SQL-Generator.git)
    ```
2.  **Install dependencies:**
    ```bash
    pip install google-genai pandas
    ```
3.  **Set up your API Key:**
    Add your `GOOGLE_API_KEY` to your environment variables or Google Colab Secrets.
4.  **Run the notebook:**
    Open `day15_NL_to_SQL_generator.ipynb` and execute the cells.

## Future Scope
* Integration with multi-table schemas and foreign key relationship mapping.
* Implementation of a front-end UI using Streamlit or Flask.
