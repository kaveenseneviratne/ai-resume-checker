#  AI Resume Critiquer

An interactive Streamlit web app that analyzes resumes using OpenAI's
GPT models. Users can upload a PDF or TXT resume and receive structured,
AI-generated feedback tailored to a specific job role.

------------------------------------------------------------------------

##  Features

-   Upload **PDF or TXT** resumes\
-   Optional job-role targeting\
-   Extracts text from resumes using **PyPDF2**\
-   Sends resume content to OpenAI for analysis\
-   Returns structured, actionable feedback\
-   Simple and clean Streamlit interface

------------------------------------------------------------------------

##  Technologies Used

-   **Python**
-   **Streamlit**
-   **OpenAI API** (gpt-4o-mini model)
-   **PyPDF2**
-   **python-dotenv**

------------------------------------------------------------------------

##  Project Structure

    project-folder/
    ├── main.py
    ├── .env            # Your API key (DO NOT upload this)
    ├── .env.example    # Template env file
    └── README.md

------------------------------------------------------------------------

##  Installation & Setup

### 1. Clone the repository

``` bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. Create and activate a virtual environment

``` bash
python3 -m venv .venv
source .venv/bin/activate   # Mac/Linux
.venv\Scripts\activate      # Windows
```

### 3. Install dependencies

``` bash
pip install -r requirements.txt
```

### 4. Add your OpenAI API key

Create a `.env` file in the project root:

    OPENAI_API_KEY=your_api_key_here

> ⚠️ **Never commit your real `.env` file.**

### 5. Run the Streamlit app

``` bash
streamlit run main.py
```

------------------------------------------------------------------------

##  How It Works

1.  User uploads a resume (PDF or TXT).\
2.  App extracts text via PyPDF2 or UTF-8 decoding.\
3.  User optionally enters a target job role.\
4.  The app sends a structured prompt to OpenAI.\
5.  OpenAI returns a detailed critique including:
    -   Content clarity\
    -   Skill presentation\
    -   Experience quality\
    -   Suggestions for improvements\
6.  Feedback is displayed cleanly in Streamlit.

------------------------------------------------------------------------

##  Environment Variables

Your `.env` file should contain:

    OPENAI_API_KEY=your_api_key_here

A `.env.example` file should be included in the repo:

    OPENAI_API_KEY=your_api_key_here

------------------------------------------------------------------------

##  Example Code Snippet

``` python
client = OpenAI(api_key=OPENAI_API_KEY)
response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[
        {"role": "system", "content": "You are an expert resume reviewer."},
        {"role": "user", "content": prompt}
    ],
    temperature=0.7,
    max_tokens=1000
)
```

------------------------------------------------------------------------

##  Contributing

Pull requests are welcome!\
To contribute: 1. Fork the repository\
2. Create a feature branch\
3. Submit a pull request

------------------------------------------------------------------------

##  License

This project is licensed under the **MIT License**.

------------------------------------------------------------------------

##  Support

If you find this project helpful, feel free to give it a ⭐ on GitHub!
