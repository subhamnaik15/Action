# 🚀 GMAIL SETUP & WORKFLOW TESTING - COMPLETE GUIDE

## ✅ CURRENT STATUS

- ✓ GitHub Actions workflows created
- ✓ Documentation added
- ✓ Test commit pushed to main branch
- ✓ Workflow should be running NOW on GitHub

---

## 📋 STEP 1: Add Gmail Credentials to GitHub (5 minutes)

### 1A: Get Your Gmail App Password

**Prerequisites:**
- Gmail account
- 2-Factor Authentication enabled on Gmail account

**Steps:**

1. Go to: **https://myaccount.google.com/security**
2. Sign in with your Gmail account
3. Look for **"App passwords"** in left menu
   - If not visible, click "2-Step Verification" first
   - Enable 2-Step Verification
4. After 2FA enabled, click "App passwords"
5. Select:
   - App: **Mail**
   - Device: **Windows Computer** (or your device type)
6. Click "Generate"
7. Google will show you a 16-character password like: `abcd efgh ijkl mnop`
8. **COPY THIS PASSWORD** - you need it next

---

### 1B: Add Secrets to GitHub

**Go to:** https://github.com/subhamnaik15/Action/settings/secrets/actions

**Click "New repository secret"** (green button on right)

**Add these 5 secrets in order:**

#### Secret 1:
```
Name:  MAIL_SERVER
Value: smtp.gmail.com
```
Click "Add secret"

#### Secret 2:
```
Name:  MAIL_PORT
Value: 465
```
Click "Add secret"

#### Secret 3:
```
Name:  MAIL_USERNAME
Value: your-email@gmail.com
```
(Replace with your actual Gmail address)
Click "Add secret"

#### Secret 4:
```
Name:  MAIL_PASSWORD
Value: abcd efgh ijkl mnop
```
(Paste your 16-character app password from Step 1A)
Click "Add secret"

#### Secret 5:
```
Name:  RECIPIENT_EMAIL
Value: your-email@gmail.com
```
(Where you want to receive build notifications)
Click "Add secret"

**Done! ✓**

---

## ⏱️ STEP 2: Monitor Your Build (4-5 minutes)

The test commit has already been pushed! GitHub Actions workflow is running NOW.

### Go here to watch the build:
**https://github.com/subhamnaik15/Action/actions**

### What to look for:

1. Click on the latest workflow run
2. Watch the build progress:
   - ✅ Checkout code
   - ✅ Setup Java 11
   - ✅ Build Release APK
   - ✅ Find APK file
   - ✅ Upload artifact
   - ✅ Send email

3. Build should take **4-5 minutes total**

### Build Status:
- 🟢 **Green checkmark** = Build successful!
- 🔴 **Red X** = Build failed (check logs)

---

## 📧 STEP 3: Check Your Email (After Build Completes)

After the build finishes (4-5 minutes), check:

1. **Your inbox** - Look for email with subject:
   - ✅ `✅ Android Build SUCCESS - Add Gmail secrets setup guide`
   - ❌ `❌ Android Build FAILED - ...` (if build fails)

2. **Spam folder** - Sometimes emails end up in spam

3. **What the email includes:**
   - Build status (SUCCESS/FAILURE)
   - APK file information (name, size)
   - Link to download APK artifact
   - Link to view build logs
   - Commit details (message, author)

---

## 📦 STEP 4: Download Your APK

Once build is successful:

1. Go to: **https://github.com/subhamnaik15/Action/actions**
2. Click on the **latest workflow run**
3. Scroll down to **Artifacts** section
4. Click **CodeAction-APK** to download
5. Extract the ZIP file to get your APK

---

## 🐛 TROUBLESHOOTING

### Build Workflow Won't Start?
- ✓ Refresh the Actions page
- ✓ May take 30-60 seconds to appear
- ✓ Check: https://github.com/subhamnaik15/Action/actions

### Build Failed?
- ✓ Click the failed workflow
- ✓ Expand the red step to see error
- ✓ Common issues:
  - Java/Gradle version mismatch
  - Missing dependencies
  - SDK version incompatibility
- ✓ Check build logs for details

### Email Not Received (After Secrets Added)?
- ✓ Wait 4-5 minutes for build to complete
- ✓ Check spam/junk folder
- ✓ Verify Gmail secrets are correct
- ✓ Try manual workflow trigger:
  - Go to Actions tab
  - Select "Android Build & Email Notification"
  - Click "Run workflow" button

### Gmail Secrets Error?
- ✓ Use **app-specific password**, NOT regular Gmail password
- ✓ Make sure 2-Step Verification is enabled
- ✓ App password should be 16 characters
- ✓ Verify MAIL_SERVER is: `smtp.gmail.com`
- ✓ Verify MAIL_PORT is: `465`

### SMTP Authentication Failed?
- ✓ Double-check MAIL_PASSWORD value
- ✓ Verify MAIL_USERNAME is correct email
- ✓ Ensure no extra spaces in secrets
- ✓ Check if Gmail account is locked (security alert)

---

## 📊 Expected Timeline

After you add the secrets, here's what happens:

```
You add GitHub Secrets
        ↓
(No new build triggered yet)
        ↓
Make next commit to main OR manually trigger
        ↓
Push to GitHub
        ↓
Workflow starts (~30 seconds)
        ↓
Java setup (~30 seconds)
        ↓
Gradle build (~2 minutes)
        ↓
APK generation (~30 seconds)
        ↓
Upload artifact (~30 seconds)
        ↓
Send email (~10 seconds)
        ↓
🎉 BUILD COMPLETE (Total: ~4-5 minutes)
        ↓
Check inbox for email
        ↓
Download APK from artifacts
```

**Note:** The test commit you just pushed will NOT send an email yet because secrets haven't been added. After you add secrets, the NEXT push will work!

---

## 🎯 Quick Summary

### What You Just Did:
1. ✅ Pushed a test commit to trigger the workflow
2. ✅ Workflow is running on GitHub NOW

### What You Need to Do:
1. **Add 5 GitHub Secrets** (5 minutes)
   - Go to: https://github.com/subhamnaik15/Action/settings/secrets/actions
   - Add MAIL_SERVER, MAIL_PORT, MAIL_USERNAME, MAIL_PASSWORD, RECIPIENT_EMAIL

2. **Make another push** (after adding secrets)
   - `git add .`
   - `git commit -m "Test after adding secrets"`
   - `git push origin main`

3. **Wait 4-5 minutes** for build

4. **Check your email** for build notification

5. **Download APK** from GitHub Actions artifacts

---

## 🔗 Important Links

- **Monitor Build**: https://github.com/subhamnaik15/Action/actions
- **Add Secrets**: https://github.com/subhamnaik15/Action/settings/secrets/actions
- **Gmail App Passwords**: https://myaccount.google.com/apppasswords
- **Gmail Security**: https://myaccount.google.com/security

---

## ⚠️ Important Notes

✓ Secrets are encrypted and only visible to you
✓ Never commit secrets to GitHub
✓ Use app-specific password for Gmail (not regular password)
✓ APK artifacts stay for 30 days
✓ Build logs are accessible anytime
✓ You can manually trigger builds anytime

---

## 🎉 Next Steps

1. **Right now**: Add the 5 GitHub Secrets ⬅️ DO THIS FIRST
2. **In 2 minutes**: Make a new commit and push
3. **In 4-5 minutes**: Check email for notification
4. **Download**: Get your APK from artifacts

---

**Questions?** Check the other documentation files:
- `SETUP_COMPLETE.md` - Overview
- `GITHUB_ACTIONS_SETUP.md` - Alternative email providers
- `CI_CD_README.md` - Complete reference

---

**Status: Ready to go! Just add secrets and you're all set! 🚀**

Created: August 13, 2026

