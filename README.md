# Email on Commit GitHub Action

This project provides a GitHub Actions workflow that automatically sends a styled HTML email notification whenever a commit is pushed to the `main` branch of your repository.

## Features

- Sends an email for every commit to the `main` branch.
- Uses a customizable HTML template ([html-template.html](html-template.html)) for beautiful notifications.
- Includes commit metadata: author, timestamp, SHA, message, and a list of changed files with direct links.
- Secure: uses repository secrets for email credentials.

## How It Works

1. **Workflow Trigger:** On every push to `main`, the workflow in [.github/workflows/main.yml](.github/workflows/main.yml) runs.
2. **Metadata Extraction:** The workflow gathers commit details and changed files.
3. **Email Sending:** A Python script fills in [html-template.html](html-template.html) with commit data and sends it via SMTP.

## Setup Instructions

1. **Clone or copy this repository.**
2. **Configure repository secrets** in your GitHub repo:
   - `EMAIL_HOST`: SMTP server (e.g., `smtp.gmail.com`)
   - `EMAIL_PORT`: SMTP port (e.g., `587`)
   - `EMAIL_USER`: Sender email address
   - `EMAIL_PASS`: Sender email password or app password
   - `EMAIL_RECIPIENTS`: Comma-separated list of recipient emails

3. **Customize the HTML template**  
   Edit [html-template.html](html-template.html) to change the email design or branding.

4. **Enable the workflow**  
   The workflow is defined in [.github/workflows/main.yml](.github/workflows/main.yml) and is ready to use.

## Example

The email includes:
- Repository name
- Commit author and timestamp
- Commit SHA (with link)
- Commit message
- List of changed files (with links to each file in the commit)
- Button to view the commit on GitHub

## Customization

- To change the email's appearance, edit [html-template.html](html-template.html).
- To modify workflow behavior, edit [.github/workflows/main.yml](.github/workflows/main.yml).

## License

MIT License

---

> This is an automated notification system powered by GitHub Actions.