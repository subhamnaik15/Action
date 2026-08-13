# GitHub Actions Setup Guide - Email Configuration

## 📧 Email Configuration Options

Choose ONE of the following options to set up email notifications:

---

## **OPTION 1: Gmail (Recommended for beginners)**

### Prerequisites:
- Gmail account
- 2-Factor Authentication enabled on Gmail

### Steps to Setup:

#### 1️⃣ Create an App-Specific Password:
1. Go to https://myaccount.google.com/security
2. Click on "App passwords" (only shows if 2FA is enabled)
3. Select "Mail" and "Windows Computer" (or your device)
4. Google will generate a 16-character password
5. Copy this password (you'll need it in Step 3)

#### 2️⃣ Add GitHub Secrets:
1. Go to: `https://github.com/subhamnaik15/Action/settings/secrets/actions`
2. Click "New repository secret"
3. Add these secrets:

| Name | Value |
|------|-------|
| `MAIL_SERVER` | `smtp.gmail.com` |
| `MAIL_PORT` | `465` |
| `MAIL_USERNAME` | Your Gmail email (e.g., `yourname@gmail.com`) |
| `MAIL_PASSWORD` | Your 16-character app password (from Step 1) |
| `RECIPIENT_EMAIL` | Where you want to receive build notifications (your email) |

---

## **OPTION 2: Generic SMTP (Office365, Yahoo, Custom Mail Server)**

### Prerequisites:
- SMTP server access
- Server address
- Port number
- Username and password

### Steps:

#### 1️⃣ Add GitHub Secrets:
1. Go to: `https://github.com/subhamnaik15/Action/settings/secrets/actions`
2. Click "New repository secret"
3. Add these secrets:

| Name | Value |
|------|-------|
| `MAIL_SERVER` | Your SMTP server (e.g., `smtp.office365.com`) |
| `MAIL_PORT` | SMTP port (usually `465` or `587`) |
| `MAIL_USERNAME` | Your email/username |
| `MAIL_PASSWORD` | Your password |
| `RECIPIENT_EMAIL` | Your email address |

### Common SMTP Servers:
- **Gmail**: `smtp.gmail.com:465`
- **Office 365**: `smtp.office365.com:587`
- **Yahoo Mail**: `smtp.mail.yahoo.com:465`
- **Outlook**: `smtp-mail.outlook.com:587`

---

## **OPTION 3: SendGrid (Free Tier Available)**

### Prerequisites:
- SendGrid account (free tier available)
- SendGrid API key

### Steps:

#### 1️⃣ Create SendGrid Account:
1. Sign up at: https://sendgrid.com
2. Go to: Settings → API Keys
3. Create a new API key
4. Copy the key

#### 2️⃣ Create Alternative Workflow:
Create a new file: `.github/workflows/build-sendgrid.yml`

(Available upon request)

---

## ✅ Verification

After adding secrets:

1. **Make a test commit to `main` branch**:
   ```bash
   git add .
   git commit -m "Setup GitHub Actions workflow"
   git push origin main
   ```

2. **Check GitHub Actions**:
   - Go to: `https://github.com/subhamnaik15/Action/actions`
   - Click on the workflow run
   - Monitor the build progress
   - Check your email for notifications

---

## 🐛 Troubleshooting

### Email not received?
- ✅ Verify secrets are correctly entered
- ✅ Check spam/junk folder
- ✅ View workflow logs for errors: Actions → Workflow run → Mail step

### Build failed?
- ✅ Check Java version compatibility (currently using JDK 11)
- ✅ Ensure gradlew has execute permissions
- ✅ Review build logs in GitHub Actions

### SMTP Authentication Error?
- ✅ For Gmail: Use app-specific password, NOT regular password
- ✅ Check port number (465 for SSL, 587 for TLS)
- ✅ Verify credentials are exact match

---

## 📝 Notes

- The workflow runs on every push to `main` branch
- You can manually trigger builds: Actions → Select workflow → Run workflow
- APK artifacts are stored for 30 days
- Build logs are available in GitHub Actions for debugging

