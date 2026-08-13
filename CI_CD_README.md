# 🚀 GitHub Actions CI/CD Pipeline - CodeAction

This repository includes automated GitHub Actions workflows for building Android APKs and sending email notifications.

## 📋 What's Included

### Workflows:
1. **`build.yml`** - Main workflow using SMTP (Gmail, Office365, Yahoo, etc.)
2. **`build-sendgrid.yml`** - Alternative workflow using SendGrid API

### Features:
✅ Automated APK build on push to `main` branch  
✅ Email notifications on build success/failure  
✅ APK artifact storage (30-day retention)  
✅ Build logs and status tracking  
✅ Manual workflow trigger option  

---

## 🎯 Quick Start (5 minutes)

### Prerequisites:
- GitHub account
- Gmail account (or other SMTP server)
- Access to repository settings

### Setup Steps:

#### 1. Choose Your Email Provider:

**Option A: Gmail (Recommended)**
- Simple setup
- No extra accounts needed
- Works reliably

**Option B: SendGrid**
- Free tier available
- Professional email service
- Better deliverability

#### 2. Add GitHub Secrets:

Go to: `https://github.com/subhamnaik15/Action/settings/secrets/actions`

**For Gmail (Option A):**
```
MAIL_SERVER = smtp.gmail.com
MAIL_PORT = 465
MAIL_USERNAME = your-email@gmail.com
MAIL_PASSWORD = your-16-char-app-password
RECIPIENT_EMAIL = your-email@gmail.com
```

**For SendGrid (Option B):**
```
SENDGRID_API_KEY = your-sendgrid-api-key
SENDGRID_FROM_EMAIL = notifications@yourdomain.com
RECIPIENT_EMAIL = your-email@gmail.com
```

#### 3. Test the Workflow:

```bash
git add .github/
git commit -m "Add GitHub Actions CI/CD pipeline"
git push origin main
```

Then go to: `https://github.com/subhamnaik15/Action/actions`

---

## 📚 Detailed Setup Guides

### For Gmail Setup:
See: [GITHUB_ACTIONS_SETUP.md](GITHUB_ACTIONS_SETUP.md) → **OPTION 1**

### For SMTP Setup:
See: [GITHUB_ACTIONS_SETUP.md](GITHUB_ACTIONS_SETUP.md) → **OPTION 2**

### For SendGrid Setup:
See: [GITHUB_ACTIONS_SETUP.md](GITHUB_ACTIONS_SETUP.md) → **OPTION 3**

---

## 🔄 Workflow Triggers

The workflows run automatically on:
- ✅ Push to `main` branch
- ✅ Pull requests to `main` branch
- ✅ Manual trigger (via GitHub Actions UI)

### Manual Trigger:
1. Go to: `https://github.com/subhamnaik15/Action/actions`
2. Select "Android Build & Email Notification"
3. Click "Run workflow"

---

## 📱 Build Artifacts

After each successful build:
- APK file is saved as a workflow artifact
- Available for download in GitHub Actions
- Stored for 30 days
- Can be extended in workflow settings

### Download APK:
1. Go to Actions → Workflow Run
2. Click "Artifacts" section
3. Download "CodeAction-APK"

---

## 📧 Email Notifications

### What You'll Receive:

**On Success:**
- ✅ Build completion notification
- 📦 APK file details (name, size)
- 🔗 Link to download APK
- 📝 Commit message and author info

**On Failure:**
- ❌ Build failure alert
- 📋 Link to build logs
- 🔍 Error details for debugging

---

## 🛠️ Customization

### Change Build Type:
Edit `.github/workflows/build.yml` line 67:
```yaml
- name: Build Release APK
  run: ./gradlew clean assembleDebug --stacktrace  # Change to assembleDebug
```

### Change Trigger Branch:
Edit `.github/workflows/build.yml` line 4-5:
```yaml
on:
  push:
    branches:
      - develop  # Change from main to develop
```

### Change Notification Frequency:
Edit `.github/workflows/build.yml` lines 82-95 to customize when emails are sent.

### Add Multiple Recipients:
In GitHub Secrets, use multiple recipients (if your email service supports it):
```
RECIPIENT_EMAIL = user1@gmail.com,user2@gmail.com
```

---

## 🔐 Security Best Practices

### ✅ DO:
- Use app-specific passwords (Gmail)
- Store credentials in GitHub Secrets
- Limit artifact retention period
- Review workflow logs regularly

### ❌ DON'T:
- Commit credentials to repository
- Use personal passwords
- Share workflow URLs publicly
- Store APKs longer than needed

---

## 🐛 Troubleshooting

### Email Not Received?
**Step 1:** Check spam/junk folder

**Step 2:** Verify secrets in:
`https://github.com/subhamnaik15/Action/settings/secrets/actions`

**Step 3:** Check workflow logs:
- Go to Actions → Recent workflow run
- Click on "Send Email" step
- View error messages

### Build Failed?
**Step 1:** Check build logs in Actions → Workflow run

**Step 2:** Common issues:
- Java version mismatch
- Gradle permissions
- Dependency issues
- SDK version conflicts

**Step 3:** Run locally to debug:
```bash
./gradlew clean assembleRelease --stacktrace
```

### SMTP Authentication Error?
- For Gmail: Use 16-character app password, NOT your regular Gmail password
- Verify MAIL_SERVER, MAIL_PORT are correct
- Check if special characters in password need escaping

---

## 📊 Monitoring Builds

### View Build History:
`https://github.com/subhamnaik15/Action/actions`

### View Specific Run:
`https://github.com/subhamnaik15/Action/actions/runs/{run-id}`

### View Build Logs:
Actions → Workflow Run → Click on any step

### Download Artifacts:
Actions → Workflow Run → Artifacts section

---

## 🚦 Workflow Status Badge

Add this to your README.md:

```markdown
[![Android Build](https://github.com/subhamnaik15/Action/workflows/Android%20Build%20%26%20Email%20Notification/badge.svg)](https://github.com/subhamnaik15/Action/actions)
```

---

## 📞 Support & Resources

- **GitHub Actions Docs:** https://docs.github.com/en/actions
- **Android Gradle Build:** https://developer.android.com/build
- **Email Action:** https://github.com/dawidd6/action-send-mail
- **SendGrid Docs:** https://sendgrid.com/docs

---

## ✨ Future Enhancements

- [ ] Add Slack notifications
- [ ] Add build time optimization
- [ ] Add automated testing
- [ ] Add multiple APK variants (debug/release)
- [ ] Add version bumping
- [ ] Add release notes generation
- [ ] Add Firebase distribution
- [ ] Add Telegram notifications

---

## 📝 License

This CI/CD configuration is part of the CodeAction project.

---

**Last Updated:** August 13, 2026  
**Workflow Version:** 1.0

