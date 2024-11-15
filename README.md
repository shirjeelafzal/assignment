# Project: Groq-based AI Summarization and Study Plan Generator

This project uses either the Groq API or OpenAI API to summarize sections of a book and generate personalized study plans. The project includes two main tasks:
- **Task 1**: Summarizing the book *Crime and Punishment* by chunking text, generating intermediate summaries, and combining them into a final summary.
- **Task 2**: Creating a customized study plan based on student details and preferences using a structured prompt template.

## Repository
GitHub Repository Link: [assignment](https://github.com/shirjeelafzal/assignment.git)

## Prerequisites
- Python 3.8+
- API Key for either Groq or OpenAI:
  - [Groq API Key](https://console.groq.com/) – You need a Groq account and an API key to access the language model.
  - OR [OpenAI API Key](https://platform.openai.com/account/api-keys) – You need an OpenAI account and an API key if you wish to use OpenAI instead.

## Installation Guide

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/shirjeelafzal/assignment.git
   cd assignment
   ```

2. **Set Up a Virtual Environment**:
   Create and activate a virtual environment for dependency management.
   ```bash
   python3 -m venv venv
   source venv/bin/activate   # On macOS/Linux
   venv\Scripts\activate      # On Windows
   ```

3. **Install Dependencies**:
   Install the required packages from `requirements.txt`.
   ```bash
   pip install -r requirements.txt
   ```

4. **Environment Variables**:
   - Rename `sample.env` to `.env`.
   - In `.env`, replace `YOUR_API_KEY` with your actual Groq or OpenAI API key, depending on which service you plan to use.
   ```bash
   GROQ_API_KEY=Your_Groq_API_KEY   # If using the Groq API
   OPENAI_API_KEY=Your_OpenAI_API_KEY   # If using the OpenAI API
   ```

   > **Note**: Only one of these API keys is needed. If using Groq, you do not need to set an OpenAI key, and vice versa.

5. **Download the Book PDF**:
   Download *Crime and Punishment* as a PDF from this link: [Download Crime and Punishment](https://drive.google.com/file/d/1WYaEoSozvUmJ_Lt5clAVs8NuSu43h9ps/view?usp=sharing). Save the file in the project root directory.

   > **Note**: This file is ignored by `.gitignore` to avoid unnecessary uploads.

## Project Structure
- **task1.ipynb**: Notebook for Task 1 – Summarizes sections of the book by processing chunks of text and combining summaries in batches.
- **task2.ipynb**: Notebook for Task 2 – Creates a personalized study plan for a student using a detailed prompt template.
- **crime-and-punishment.pdf**: Book used in Task 1 for text extraction and summarization.
- **sample.env**: Template for storing your API key securely.
- **requirements.txt**: Lists dependencies necessary for the project.

## Running the Notebooks
After setup, open and run the notebooks in your environment.

1. **Run Task 1**:
   - In `task1.ipynb`, the document loader reads the "Crime and Punishment" PDF, splits it into chunks, and processes each chunk using the Groq or OpenAI API to create summaries.
   - The summaries are batched and compiled into a final PDF file.
   
2. **Run Task 2**:
   - In `task2.ipynb`, a personalized study plan template is used to generate a study plan for a student based on their information, such as field of study, learning style, goals, and challenges.

**Note**: Due to API limits, it may be necessary to handle rate-limiting errors. The current code attempts to reduce the frequency of API calls.

## Troubleshooting
- **Rate Limit Error**: If you encounter `rate_limit_exceeded` errors, pause the execution and try again after the specified cooldown period.
- **PDF Encoding Error**: If a `UnicodeEncodeError` occurs, refer to solutions in the notebook that handle encoding issues using UTF-8.