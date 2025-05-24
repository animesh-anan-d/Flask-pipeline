# Jenkins Pipeline for Flask Application

## Pipeline Stages

1. **Build:** Installs Python dependencies using `pip install -r requirements.txt`.
2. **Test:** Runs unit tests using `pytest`.
3. **Deploy:** Deploys application if tests pass (stub - add your own commands).
4. **Notifications:** Sends email alerts on build success or failure.

## Prerequisites

- Jenkins server with Git and Python installed.
- Jenkins plugins: Git, Email Extension (or Email Notification).
- SMTP server setup in Jenkins (e.g., Gmail SMTP with app password).
- Python virtual environment supported on build agents.
- GitHub repository with Jenkinsfile in root directory.

## How to Trigger

- Pipeline triggers automatically on push to `main` branch.

## Email Configuration

- SMTP Server: smtp.gmail.com  
- Port: 587  
- Use TLS: true  
- Authentication: Jenkins credentials with Gmail app password.

