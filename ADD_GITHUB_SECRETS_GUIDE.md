# 🔐 How to Add GitHub Secrets for Gmail

## Quick Steps:

### 1. Go to GitHub Secrets Page
**URL**: https://github.com/subhamnaik15/Action/settings/secrets/actions

### 2. Click "New repository secret" (Green Button)

### 3. Add These 5 Secrets (One by One):

#### Secret #1:
- **Name**: `MAIL_SERVER`
- **Value**: `smtp.gmail.com`
- Click "Add secret"

#### Secret #2:
- **Name**: `MAIL_PORT`
- **Value**: `465`
- Click "Add secret"

#### Secret #3:
- **Name**: `MAIL_USERNAME`
- **Value**: `your-email@gmail.com` (replace with your Gmail)
- Click "Add secret"

#### Secret #4:
- **Name**: `MAIL_PASSWORD`
- **Value**: `abcd efgh ijkl mnop` (your 16-character app password from Google)
- Click "Add secret"

#### Secret #5:
- **Name**: `RECIPIENT_EMAIL`
- **Value**: `your-email@gmail.com` (where you want notifications sent)
- Click "Add secret"

### Done! ✅

After adding all 5 secrets, you're ready to test the workflow!

---

## ⚠️ Important Notes:

- Use **app-specific password**, NOT your regular Gmail password
- If you don't have 2FA enabled, you need to enable it first
- Secrets are encrypted and only you can see them
- App passwords can be managed at: https://myaccount.google.com/apppasswords

