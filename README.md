# 🔔 GitHub Repo Notifier

Automatically monitor your GitHub repositories and get email alerts when new ones are created.

This Python tool uses the **GitHub API** to detect new repositories and sends email notifications via **Gmail SMTP**. Ideal for developers who want to track their GitHub presence or automate team-wide alerts.

---

## 📦 Features

- ✅ Monitors GitHub for newly created repositories
- 📬 Sends real-time email notifications
- 🧠 Keeps track of already-notified repositories using a local JSON file
- ⏲️ Easily automated with `cron` for scheduled checks

---

## 📁 Project Structure

```
github-repo-notifier/
├── github_repo_notifier.py    # Main script
├── repos.json                 # Tracks notified repos
├── log.txt                    # Logs script output
├── .env                       # Stores credentials securely
├── .gitignore
└── README.md
```

---

## ⚙️ Setup Instructions

### ✅ 1. Clone the Repository

```bash
git clone https://github.com/Priyanshu-1477/github-repo-notifier.git
cd github-repo-notifier
```

---

### 🔐 2. Create a `.env` File

In the root of the project (`github-repo-notifier/`), create a file named `.env` with the following content:

```env
GITHUB_USERNAME=your-github-username
GITHUB_TOKEN=your-personal-access-token
SENDER_EMAIL=your@gmail.com
APP_PASSWORD=your-gmail-app-password
RECEIVER_EMAIL=receiver@example.com
```

> - **GitHub Token:** [Generate a GitHub PAT](https://github.com/settings/tokens) (read-only access is sufficient)  
> - **Gmail App Password:** [Generate a Gmail App Password](https://myaccount.google.com/apppasswords) if using 2FA

---

### 📦 3. Install Python Dependencies

Make sure Python 3 and pip are installed. Then run:

```bash
pip install -r requirements.txt
```

If `requirements.txt` doesn't exist, use this content:

```txt
requests
rich
python-dotenv
```

---

### ▶️ 4. Run the Script

```bash
python3 github_repo_notifier.py
```

You should see colored terminal output. If any new repositories are found, an email notification will be sent.

---

### 🔁 5. Automate with Cron (Optional)

To run the script automatically every 10 minutes:

1. Open your crontab:

```bash
crontab -e
```

2. Add this line (update the full path to your script and Python binary):

```bash
*/10 * * * * /usr/bin/python3 /home/yourusername/github-repo-notifier/github_repo_notifier.py >> /home/yourusername/github-repo-notifier/log.txt 2>&1
```

> 🔁 Make sure you replace `/home/yourusername/` with the **actual absolute path** to your cloned project directory.

---

### 🔒 .gitignore

These files are excluded from version control:

```gitignore
.env
log.txt
repos.json
```

---

## 🧪 Troubleshooting

- **No email sent?**  
  Ensure the Gmail App Password is correct and `RECEIVER_EMAIL` is a valid address.

- **Script fails silently?**  
  Check `log.txt` for any errors. Make sure the `.env` file is present and formatted correctly.

- **Still not working?**  
  Try running the script manually and paste any errors from terminal output in the issues section of this repo explaining the problem faced and the command you typed.

---

## 📄 License

**MIT License** – Free to use, modify, and distribute.
