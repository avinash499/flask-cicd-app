# Copilot Instructions for flask-cicd-app

## Project Overview
This is a minimal Flask web application designed for CI/CD demonstration. The app serves a single route (`/`) rendering an HTML template. It is containerized using Docker and intended to run with Gunicorn in production.

## Architecture
- **app.py**: Main Flask application. Entry point for both local and containerized runs.
- **templates/index.html**: HTML template rendered at the root route.
- **tests/test_app.py**: Unit tests using `unittest` for basic route validation.
- **requirements.txt**: Python dependencies (Flask, Gunicorn, Requests, etc.).
- **Dockerfile**: Builds a slim Python image, installs dependencies, and runs the app with Gunicorn.

## Developer Workflows
- **Local Development**: Run `python app.py` to start the Flask server with debug mode enabled.
- **Containerized Production**: Build and run the Docker image. The app is served via Gunicorn on port 5000.
- **Testing**: Run tests with `python -m unittest discover tests`.
- **Dependency Management**: Update `requirements.txt` and rebuild the Docker image for changes.

## Patterns & Conventions
- All routes are defined in `app.py`. No blueprints or modularization.
- HTML templates are stored in `templates/`.
- Tests are located in `tests/` and use the Flask test client.
- The Dockerfile expects the app to be named `app.py` and the Flask instance to be called `app`.
- Gunicorn is used for production serving; Flask's built-in server is only for development.

## Integration Points
- No database or external service integration in the current codebase.
- Environment variables can be managed via `python-dotenv` if needed (see `requirements.txt`).

## Example Commands
- **Run locally:**
  ```powershell
  python app.py
  ```
- **Run tests:**
  ```powershell
  python -m unittest discover tests
  ```
- **Build Docker image:**
  ```powershell
  docker build -t flask-cicd-app .
  ```
- **Run Docker container:**
  ```powershell
  docker run -p 5000:5000 flask-cicd-app
  ```

## Key Files
- `app.py`, `Dockerfile`, `requirements.txt`, `tests/test_app.py`, `templates/index.html`

---
If any conventions or workflows are unclear or missing, please provide feedback to improve these instructions.
