# SnapClass

SnapClass is an AI-assisted classroom attendance product. This repository currently
serves a Flask landing page and also contains the source modules for the Streamlit
attendance experience.

## What is in this repository?

- `app.py` is the Flask entry point. It serves `templates/index.html` at `/`.
- `templates/index.html` is the public product page for SnapClass.
- `static/` contains the landing page stylesheet, JavaScript, fonts, logo, and demo images.
- `src/screens/` contains the Streamlit student, teacher, and home screens.
- `src/components/` contains reusable Streamlit UI components and dialogs.
- `src/pipelines/` contains the face and voice attendance processing modules.
- `src/database/` contains database configuration and persistence helpers.
- `vercel.json` configures deployment of the Flask app with Vercel's Python runtime.

## Run locally

Create and activate a virtual environment, then install the dependencies:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

Start the Flask landing page:

```powershell
python app.py
```

Open <http://127.0.0.1:5002/> in a browser. The application runs with Flask's
development server and listens on port `5002`.

## Deployment

The configured Vercel entry point is `app.py`. Vercel routes all requests to that
Flask application. The landing page's call-to-action currently links to the hosted
Streamlit application at `https://snapclass.streamlit.app/`.

## Development notes

The landing page and the Streamlit application are separate runtime surfaces in the
current repository. `requirements.txt` currently lists only the Flask deployment
dependencies, so running the modules under `src/` may require adding their Streamlit,
database, computer-vision, and audio dependencies and providing the expected
environment variables. The Streamlit application does not currently have a root
launcher file in this repository.

