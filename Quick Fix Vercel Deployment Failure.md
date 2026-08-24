# Quick Fix: Vercel Deployment Failure


### 1. Set the Correct Email
Run these commands in your project terminal, replacing the email with the one linked to your **original Vercel/GitHub account**:

```bash
git config user.email "your_original_email@example.com"
git config user.name "Your Original Name"
```

### 2. Fix the Last Commit
Update the most recent commit to use the new email identity.

**Option A: Amend the existing commit (Cleanest history)**
*Use this if you are the only one working on this branch.*
```bash
git commit --amend --reset-author --no-edit
git push --force origin main
```

**Option B: Add a new fix commit (Safest)**
*Use this if others are working on the branch or you want to avoid force-pushing.*
```bash
git commit --allow-empty -m "Fix: Trigger Vercel deployment with correct author"
git push origin main
```

### 3. Verify Deployment
Go to your Vercel dashboard. The deployment should now trigger automatically. If it does not, manually retry the failed deployment in the Vercel UI.

