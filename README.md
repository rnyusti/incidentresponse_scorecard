# Incident Response Scorecard - Interactive 2026

An interactive web-based incident response evaluation and compliance tracking system.

## Features

✅ **GitHub Authentication** - Secure read-only access  
✅ **Save Progress to GitHub** - Persist data directly to your repository  
✅ **Multi-Month Tracking** - Track incidents across all 12 months  
✅ **Weighted Scoring** - Automatic calculation with configurable weights  
✅ **Real-time Summaries** - Live compliance percentages and scores  
✅ **CSV Export** - Download data for analysis  
✅ **Local Storage** - Automatic saving to browser  
✅ **Print Support** - Print scorecards anytime  

## Quick Start

### 1. Create a GitHub Repository

```bash
# Create a new repo on github.com or use an existing one
# Clone it locally
git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
cd YOUR_REPO
```

### 2. Add the Scorecard Files

Copy `index.html` and `.github/workflows/deploy.yml` to your repository:

```bash
# Copy files from this project
cp index.html .
cp -r .github .
git add .
git commit -m "Add incident response scorecard"
git push origin main
```

### 3. Enable GitHub Pages

1. Go to your repository settings
2. Scroll to "Pages"
3. Select "Deploy from a branch"
4. Choose `main` branch and `/root` folder
5. Click Save

### 4. Set Up GitHub Pages Deployment

The workflow file (`.github/workflows/deploy.yml`) will automatically deploy your site when you push changes.

## How to Use

### Authentication Setup

1. Click **🔐 Sign In with GitHub** button
2. Paste your GitHub credentials in this JSON format:
   ```json
   {"owner":"YOUR_USERNAME","repo":"YOUR_REPO","token":"YOUR_PAT"}
   ```

### Create a Personal Access Token (PAT)

1. Go to [github.com/settings/tokens](https://github.com/settings/tokens)
2. Click "Generate new token (classic)"
3. Select scopes:
   - `public_repo` (for public repositories)
   - `repo` (for private repositories)
4. Copy and use the token

### Save Progress

1. Sign in with your GitHub credentials
2. Fill in your scorecard data
3. Click **💾 Save Progress to GitHub**
4. Data saves to `data/scorecard_YYYY-MM.json` in your repo

### Features

- **Add Incidents**: Click ➕ Add Incident to track more incidents
- **Month Navigation**: Switch between months using tabs
- **Pagination**: Navigate through large incident lists
- **Real-time Calculations**: Scores update automatically
- **Local Backup**: Data auto-saves to browser localStorage

## Scoring System

| Value | Meaning | Score |
|-------|---------|-------|
| **1** | Yes/Pass | 100% of weight |
| **0.5** | Partial | 50% of weight |
| **0** | No/Fail | 0% |
| **N/A** | Not Applicable | Excluded from total |

## Data Storage

- **Browser**: Auto-saves locally for immediate access
- **GitHub**: Manual save to your repository for backup and sharing
- **Exports**: CSV and JSON formats available

## Categories Tracked

1. **Incident Declaration & Early Response**
2. **Incident Communication & Coordination**
3. **Statuspage Communication**
4. **Resolution & Post-Incident Actions**

## Security Notes

⚠️ **Read-Only Mode**: The interface doesn't allow editing from GitHub directly - all changes happen locally and are saved back.

✅ **Token Security**: 
- Never share your PAT
- Use environment-specific tokens if possible
- Revoke tokens at [github.com/settings/tokens](https://github.com/settings/tokens) anytime

## Troubleshooting

**"Save to GitHub" button doesn't appear?**
- Ensure you've signed in successfully
- Check your browser console (F12) for errors

**Data not saving?**
- Verify your PAT hasn't expired
- Check repository permissions
- Ensure the `data/` folder exists in your repo (create it if needed)

**GitHub Pages not deploying?**
- Check the "Actions" tab in your repository
- Ensure workflow has proper permissions
- Verify Pages settings in repository settings

## File Structure

```
your-repo/
├── index.html                 # Main scorecard application
├── README.md                  # This file
├── .github/
│   └── workflows/
│       └── deploy.yml         # GitHub Pages deployment
└── data/                      # Scorecard data (auto-created)
    ├── scorecard_2026-01.json
    ├── scorecard_2026-02.json
    └── ...
```

## Support

For issues or feature requests, please create an issue in your repository.

## License

This project is provided as-is for incident response tracking and evaluation.
