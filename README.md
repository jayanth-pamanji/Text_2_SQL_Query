🧠 SQL-LLM with Google Gemini & Streamlit

This project is a simple Text-to-SQL application built with Google Gemini and Streamlit. It allows users to ask questions in plain English, which are then converted into SQL queries using Gemini, executed on a local SQLite database, and the results are displayed in a web UI.

🚀 Features

Converts natural language questions into SQL queries using Google Gemini Pro.

Executes SQL queries on a SQLite database (student.db).

Displays query results in a Streamlit web app.

Example supported queries:

"How many entries of records are present?" → SELECT COUNT(*) FROM STUDENT;

"Tell me all the students studying in Data Science class?" → SELECT * FROM STUDENT WHERE CLASS="Data Science";

🛠️ Tech Stack

Python 3.9+

Streamlit – for web UI

SQLite – for database

Google Generative AI (Gemini-Pro) – for natural language → SQL query conversion

dotenv – for managing API keys

📂 Project Structure
sqlllm/
│-- app.py                # Main Streamlit app
│-- student.db            # SQLite database (with STUDENT table)
│-- .env                  # Stores your GOOGLE_API_KEY
│-- requirements.txt      # Dependencies
│-- README.md             # Project documentation



Install dependencies

pip install -r requirements.txt


Set up environment variables

Create a .env file in the project root:

GOOGLE_API_KEY=your_google_gemini_api_key_here


Run the Streamlit app

streamlit run app.py


Open your browser at http://localhost:8501 to use the app. 🎉

🗄️ Database (student.db)

The SQLite database student.db should contain a table named STUDENT with the following schema:

CREATE TABLE STUDENT (
    NAME TEXT,
    CLASS TEXT,
    SECTION TEXT
);


You can insert sample data:

INSERT INTO STUDENT (NAME, CLASS, SECTION) 
VALUES ('Alice', 'Data Science', 'A'),
       ('Bob', 'AI', 'B'),
       ('Charlie', 'Data Science', 'A');

📌 Example Usage

Type in:

How many entries of records are present?


✅ Output: Number of rows in the STUDENT table.

Type in:

Tell me all the students studying in Data Science class?


✅ Output: List of students in Data Science class.

📜 Requirements

Create a requirements.txt with:

streamlit
python-dotenv
google-generativeai
sqlite3-bro
