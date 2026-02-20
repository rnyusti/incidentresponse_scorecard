# 🚀 Setup Guide - GitHub Hosting & Authentication

## Complete Step-by-Step Setup

### Step 1: Create a GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Fill in:
   - **Repository name**: `incident-scorecard` (or any name)
   - **Description**: "Interactive Incident Response Scorecard"
   - **Public** (if you want GitHub Pages to be public)
   - Check "Add a README file"
3. Click "Create repository"

### Step 2: Upload Your Scorecard Files

**Option A: Using Git (Recommended)**

```bash
# Clone your new repo
git clone https://github.com/YOUR_USERNAME/incident-scorecard.git
cd incident-scorecard

# Copy these files:
# - index.html
# - README.md
# - package.json
# - .gitignore
# - .github/workflows/deploy.yml

# Add and commit
git add .
git commit -m "Add incident response scorecard"
git push origin main
```

**Option B: Using GitHub Web Interface**

1. In your repository, click "Add file" → "Upload files"
2. Drag and drop: `index.html`, `README.md`, `package.json`, `.gitignore`
3. Click "Commit changes"

### Step 3: Enable GitHub Pages

1. Go to your repository
2. Click **Settings** tab
3. Scroll down to **"Pages"**
4. Under "Build and deployment":
   - **Source**: Select "Deploy from a branch"
   - **Branch**: Select `main`
   - **Folder**: Select `/ (root)`
5. Click **Save**

Your site will be live at: `https://YOUR_USERNAME.github.io/incident-scorecard`

### Step 4: Generate GitHub Personal Access Token

1. Go to [github.com/settings/tokens](https://github.com/settings/tokens)
2. Click **"Generate new token"** → **"Generate new token (classic)"**
3. Fill in:
   - **Note**: `incident-scorecard-token`
   - **Expiration**: 90 days or Custom
4. Select scopes:
   - ☑️ `public_repo` (for public repos)
   - ☑️ `repo` (if using private repo)
5. Scroll down and click **"Generate token"**
6. **Copy the token immediately** (you won't see it again!)

### Step 5: Use the Scorecard

1. Open your GitHub Pages site: `https://YOUR_USERNAME.github.io/incident-scorecard`
2. Click **🔐 Sign In with GitHub**
3. Enter your credentials as JSON:
   ```json
   {
     "owner": "YOUR_USERNAME",
     "repo": "incident-scorecard",
     "token": "ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
   }
   ```
4. Click OK
5. Now you can:
   - Fill in your scorecard data
   - Click **💾 Save Progress to GitHub** to backup data

### Step 6: Verify Setup

✅ **Check if everything works:**

1. Fill in some test data
2. Click **💾 Save Progress to GitHub**
3. You should see a ✅ confirmation
4. Go to your GitHub repo's **Code** tab
5. Look for a `data/` folder with `scorecard_2026-02.json` file
6. You can click on it to view your saved data!

## 🔐 Security & Privacy

### Your Data

- **Local Storage**: Data saved locally to your browser for working offline
- **GitHub**: Only saved when you explicitly click "Save Progress"
- **Your Token**: Only used for saving; never stored permanently
- **Read-Only Interface**: You can't accidentally edit from GitHub

### Token Management

- **Revoke anytime**: [github.com/settings/tokens](https://github.com/settings/tokens)
- **Limit scope**: Use `public_repo` only if repo is public
- **Set expiration**: Recommend 90 days for security
- **Don't share**: Treat like a password

## ⚙️ Advanced Setup (Optional)

### Auto-Deploy from GitHub

The `.github/workflows/deploy.yml` file already handles this! Every time you push, your changes automatically deploy to GitHub Pages.

### Using Custom Domain

Edit `.github/workflows/deploy.yml`:

```yaml
with:
  github_token: ${{ secrets.GITHUB_TOKEN }}
  publish_dir: ./
  cname: scorecard.yourcompany.com  # Add this line
```

Then update DNS settings (varies by provider).

## 🆘 Troubleshooting

### "Save to GitHub" button not showing?

```
✓ Click "Sign In with GitHub"
✓ Verify you pasted the JSON correctly
✓ Check browser console (F12 → Console tab)
```

### Token expired or invalid?

1. Go to [github.com/settings/tokens](https://github.com/settings/tokens)
2. Click "Regenerate" or create a new one
3. Update your credentials in the app

### Site not loading?

1. Check repo is public (or you have access)
2. Wait 2-3 minutes after enabling Pages
3. Try `https://YOUR_USERNAME.github.io/incident-scorecard/index.html`
4. Check the **Actions** tab for deployment errors

### Data not saving?

```
✓ Verify token has "repo" scope
✓ Check repo name is exactly correct
✓ Ensure "data/" folder was created
✓ Check browser console for error messages
```

## 📚 Usage Tips

### Monthly Organization

1. Use month tabs to switch between January-December
2. Data is automatically saved per month locally
3. Save to GitHub when you want to backup

### Adding Incidents

- Click **➕ Add Incident**
- Click incident number to edit/rename
- Can track unlimited incidents per month

### Exporting Data

- **CSV**: Click **💾 Export as CSV** (great for Excel)
- **JSON**: Click **💾 Save Document** (raw data backup)
- **GitHub**: Click **💾 Save Progress to GitHub** (cloud backup)

### Printing

- Click **🖨️ Print** for paper copies
- Browser print dialog opens (Ctrl+P / Cmd+P)

## 🎯 Next Steps

1. ✅ Create GitHub repo
2. ✅ Upload files
3. ✅ Enable GitHub Pages
4. ✅ Create Personal Access Token
5. ✅ Open the scorecard and sign in
6. ✅ Save your first progress to GitHub!

## 📞 Support

If you encounter issues:

1. Check **Settings** → **Pages** (should show live URL)
2. Check **Actions** tab for deployment status
3. Review browser **Console** (F12) for JavaScript errors
4. Try clearing browser cache (Ctrl+Shift+Delete)

---

**You're all set!** 🎉

Your interactive scorecard is now:
- 🌐 Hosted on GitHub Pages (free)
- 🔐 Secure with GitHub authentication
- 💾 Backed up to your repository
- 📱 Accessible from anywhere

Happy incident tracking! 📊
