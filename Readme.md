# N8N Lead Capture Form

This repository contains a **GitHub Pages–ready** static contact form that sends form data to an n8n webhook.

## Files

- **index.html** – The HTML/CSS/JavaScript for the form.
- **README.md** – This documentation file.

## Setup Instructions

1. **Clone or download** this repository.
2. **Replace the webhook URL**  
   In `index.html`, find `YOUR_N8N_WEBHOOK_URL_HERE` and replace it with your n8n webhook URL (e.g. `https://n8n.example.com/webhook-lead-capture`).
3. **Commit & push** to GitHub  
git init
git add index.html README.md
git commit -m "Add contact form"
git branch -M main
git remote add origin https://github.com/<YOUR_USERNAME>/<REPO_NAME>.git
git push -u origin main

4. **Enable GitHub Pages**  
- Go to your repo Settings → Pages  
- Under “Source” select the `main` branch and root directory  
- Click **Save**  
5. **Visit your live form** at  
`https://<YOUR_USERNAME>.github.io/<REPO_NAME>/`

## Usage

- Fill out the form and click **Send Message**  
- On success, a confirmation appears  
- The form data posts as JSON to your n8n webhook

## License

MIT License – Feel free to use and modify as needed.
