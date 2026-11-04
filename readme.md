# 🧠 Quiz Generator from Notes

A Streamlit app that turns your study notes into a practice quiz using Google Gemini.

## Features

- Paste notes or upload a **PDF, DOCX or TXT** file
- Choose the number of questions (3-20), difficulty (Easy / Medium / Hard) and type (Multiple choice / True-False)
- Answer the quiz in the app and get an **instant score**
- Review every question with the correct answer and a short explanation
- Retake the quiz or download it with the answer key (Markdown)
- Answer options are shuffled so the correct answer is not always in the same place

## Tech stack

Python, Streamlit, Google Gemini API (Google AI Studio key), pypdf, python-docx.

## Project structure

```
quiz-generator/
├── app.py
├── requirements.txt
└── README.md
```

## Run locally

1. Install Python 3.10 or newer.
2. In a terminal inside the project folder:
   ```bash
   python -m venv venv
   venv\Scripts\activate          # Mac/Linux: source venv/bin/activate
   pip install -r requirements.txt
   ```
3. Get a free API key from [Google AI Studio](https://aistudio.google.com/apikey).
4. Paste the key in the app sidebar, or create `.streamlit/secrets.toml`:
   ```toml
   GOOGLE_API_KEY = "your-key-here"
   ```
5. Run:
   ```bash
   streamlit run app.py
   ```

## Push to GitHub using the website

1. Sign in at [github.com](https://github.com).
2. Click **+** (top right) → **New repository**.
3. Name it `quiz-generator`, choose **Public**, click **Create repository**.
4. Click **uploading an existing file**.
5. Drag in `app.py`, `requirements.txt` and `README.md`.
6. Add a message like `Add quiz generator` and click **Commit changes**.

The file must be named exactly `requirements.txt` (all lowercase, with an "s").
Never upload your API key or `secrets.toml`.

## Deploy on Streamlit Community Cloud

1. Go to [share.streamlit.io](https://share.streamlit.io) and click **Continue with GitHub**.
2. Click **Create app** → **Deploy a public app from GitHub**.
3. Choose your repository, branch `main`, main file path `app.py`.
4. Click **Advanced settings**, pick Python 3.11 or 3.12, and in **Secrets** paste:
   ```toml
   GOOGLE_API_KEY = "your-key-here"
   ```
5. Click **Save**, then **Deploy**.

To change the key later: **Manage app → Settings → Secrets**.

## Troubleshooting

| Problem | Fix |
|---|---|
| `ModuleNotFoundError` | Check that `requirements.txt` is in the repo root with the exact name and contents, then **Manage app → Reboot app**. |
| "Not enough text to make a quiz" | Add more notes. Scanned-image PDFs have no text, so use a text-based PDF, DOCX or TXT. |
| "Quiz generation failed" | Check the API key and the model name in the sidebar. |
| Quota or rate-limit error | Free keys have limits. Wait a minute and try again. |
| Fewer questions than requested | Short notes cannot support many questions. Add more notes or generate again. |

## Privacy

Your notes are sent to the Gemini API to write the questions. The app does not store them.

## Ideas for improvement

- Add a timer for each question
- Save scores over time
- Export the quiz as PDF
- Add flashcard mode

## License

MIT
