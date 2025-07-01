# 🔔 GitHub Repo Notifier

A Python automation tool that **tracks your GitHub repositories** and **sends email alerts** when a new repository is added. Powered by GitHub API + Gmail SMTP.

---

## 📦 Features

- Detects new repositories using GitHub API
- Sends email notifications automatically
- Keeps a local record of already notified repos
- Can run on a schedule via cron

---

## ⚙️ Setup

### 1. Create a `.env` file with:
- GITHUB_USERNAME=your-username
- GITHUB_TOKEN=your-token
- SENDER_EMAIL=your@gmail.com
- APP_PASSWORD=your-gmail-app-password
- RECEIVER_EMAIL=friend@example.com

```yaml
> Use a [GitHub PAT](https://github.com/settings/tokens)  
> Use a [Gmail App Password](https://myaccount.google.com/apppasswords)
```

---

### 2. Install Dependencies

```bash
pip install requests rich python-dotenv
```

### 3. Automate with Cron
```bash
*/10 * * * * /usr/bin/python3 /home/yourname/repo_notifier_clean/github_repo_notifier.py >> /home/yourname/repo_notifier_clean/log.txt 2>&1
```

### 🚫 .gitignore Protects:
```pgsql
.env
log.txt
repos.json
```

## 📄 License
MIT – Free to use, modify, and share.


