README
This repository contains a GitHub Pages-ready static contact form that sends form data to an n8n webhook.

Files
index.html: The complete HTML, CSS, and JavaScript code for the form.

Setup Instructions
Clone or Download this repository to your local machine.

Replace Webhook URL

Open index.html.

Locate YOUR_N8N_WEBHOOK_URL_HERE in the JavaScript section.

Replace with your actual n8n webhook URL (e.g., https://n8n.example.com/webhook-lead-capture).

Commit & Push to GitHub

bash
git init
git add index.html README.md
git commit -m "Initial commit: Add static contact form"
git branch -M main
git remote add origin https://github.com/<YOUR_USERNAME>/<REPO_NAME>.git
git push -u origin main
Enable GitHub Pages

Go to your repository on GitHub.

Click Settings → Pages.

Select Deploy from a branch.

Choose main branch and root folder.

Click Save.

Access Your Form

Your form will be live at https://<YOUR_USERNAME>.github.io/<REPO_NAME>/.

Usage
Fill out the form fields and click Send Message.

On successful submission, a confirmation message appears.

Form data is sent as JSON to your n8n webhook for further processing.

License
This project is licensed under the MIT License. Feel free to use and modify it for your own purposes.
