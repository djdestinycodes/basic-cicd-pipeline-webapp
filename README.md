
# Flask CI/CD Pipeline Project

---

## Overview

This project demonstrates a simple **CI/CD pipeline** using Flask, GitHub, and Render.com with a **staging and production environment** workflow.

You will learn how to:

- Use Git branches (`develop` & `main`) for safe deployment workflows  
- Deploy Python Flask apps automatically with Render  
- Manage staging and production environments separately  
- Understand basic CI/CD concepts with a hands-on example  

---

## Tech Stack

| Technology    | Purpose                      | Logo |
|---------------|------------------------------|------|
| Python        | Backend programming language | ![Python](https://www.vectorlogo.zone/logos/python/python-icon.svg) |
| Flask         | Web framework                | ![Flask](https://www.vectorlogo.zone/logos/pocoo_flask/pocoo_flask-icon.svg) |
| Git & GitHub  | Version control & repo host  | ![GitHub](https://www.vectorlogo.zone/logos/github/github-icon.svg) |
| Render.com    | Cloud platform for hosting   | ![Render](https://render.com/favicon.ico) |
| Markdown      | Documentation formatting     | ![Markdown](https://upload.wikimedia.org/wikipedia/commons/4/48/Markdown-mark.svg) |

---

## File Structure

```
/your-project-root
│
├── app/
│   └── app.py            # Flask application code
├── requirements.txt      # Python dependencies
└── README.md             # Project documentation
```

---

## Flask App Code

The simple Flask app responds with a message at the root endpoint `/`:

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Hello from Flask CI/CD! You are running your First CI/CD Pipeline!"

if __name__ == "__main__":
    app.run(debug=True, host="0.0.0.0", port=5001)
```

---

## How It Works

### Branch Strategy & Render Environments

- **`develop` branch**: For ongoing development and testing; deploys to **staging** environment on Render  
- **`main` branch**: For stable, production-ready code; deploys to **production** environment on Render

### Workflow

1. Make code changes in your local environment (e.g., VS Code).
2. Commit and push to the `develop` branch.
3. Render auto-deploys to the staging URL for testing.
4. After successful testing, merge `develop` into `main`.
5. Render auto-deploys to the production URL for live use.

---

## Deployment Instructions

### Local Development

```bash
# Clone repo and switch to develop branch
git clone https://github.com/yourusername/your-repo.git
cd your-repo
git checkout develop

# Install dependencies
pip install -r requirements.txt

# Run the Flask app locally
python app/app.py
```

### Push Code & Deploy

```bash
# Commit changes to develop branch
git add .
git commit -m "Your commit message"
git push origin develop

# After testing, merge to main branch
git checkout main
git merge develop
git push origin main
```

---

## Notes

- This is a demo and uses Flask’s development server. For production, use a production WSGI server (e.g., Gunicorn).  
- Render free tier is used for deployment; no SSH access is available.  
- Customize your Render services to link branches accordingly.

---

## Learning Resources

- [Flask Documentation](https://flask.palletsprojects.com/)  
- [Render.com Docs](https://render.com/docs)  
- [GitHub Branching Guide](https://docs.github.com/en/get-started/using-git/about-branches)  
- [CI/CD Concepts](https://www.redhat.com/en/topics/devops/what-is-ci-cd)  

---

## License

This project is open-source and free to use.

---

*Created by Girish Vilvankadu Jesudas*
