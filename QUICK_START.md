# Quick Reference

## 🚀 5-Minute Setup

1. **Create repo**: [github.com/new](https://github.com/new)
2. **Upload files** (use GitHub web interface or git push)
3. **Enable Pages**: Settings → Pages → Deploy from branch (main)
4. **Create token**: [github.com/settings/tokens](https://github.com/settings/tokens) → Generate token (classic)
   - Scopes: `public_repo` or `repo`
5. **Open site** (wait 2-3 min): `https://USERNAME.github.io/repo-name`
6. **Sign in** with: `{"owner":"USERNAME","repo":"repo-name","token":"ghp_..."}`

## 📊 Using the Scorecard

### Data Entry
- Enter `1` = Pass/Yes (green) ✅
- Enter `0` = Fail/No (red) ❌  
- Enter `0.5` = Partial (yellow) ⚠️
- Leave blank = Not filled

### Saving
- **Local**: Auto-saves to browser (works offline)
- **GitHub**: Click "💾 Save Progress to GitHub" to backup
- **Export**: CSV or JSON downloads anytime

### Navigation
- **Months**: Click month tabs at top
- **Incidents**: Use arrow buttons to scroll columns
- **Summary**: View all incident scores at bottom

## 🔐 Authentication

### First Time
```json
{
  "owner": "your_username",
  "repo": "your_repo_name",
  "token": "ghp_paste_your_token_here"
}
```

### Sign Out
Click "🔓 Sign Out" button

### Token Help
- Create: [github.com/settings/tokens](https://github.com/settings/tokens)
- Revoke: Same link, click revoke
- Recreate: No limit on new tokens

## 🆘 Quick Fixes

| Problem | Fix |
|---------|-----|
| Site not loading | Wait 2-3 min after enabling Pages |
| Save button missing | Click "Sign In" first |
| Save fails | Check token + repo name |
| Data disappeared | Check localStorage (F12 → Storage) |
| Can't edit cells | Reload page (F5) |

## 📁 File Structure

```
repo/
├── index.html              ← Main scorecard
├── README.md               ← Documentation
├── SETUP.md                ← Setup guide (this file)
├── package.json            ← Project info
├── .gitignore              ← What to ignore
├── .github/
│   └── workflows/
│       └── deploy.yml      ← Auto-deploy to Pages
└── data/                   ← Your saved data
    └── scorecard_2026-XX.json
```

## 💡 Pro Tips

1. **Backup Often**: Click "Save Progress to GitHub" regularly
2. **CSV Export**: Great for sharing with others in Excel
3. **Print Monthly**: Use "🖨️ Print" for reports
4. **Edit Incident Name**: Click the incident number (#1964) in header
5. **Add More Incidents**: Click "➕ Add Incident"
6. **Clear Data**: Use "🔄 Clear All Data" (can't undo!)

## 🌐 Sharing Your Data

**With Others:**
1. Save to GitHub
2. Share repo link
3. They can view `data/scorecard_YYYY-MM.json` files
4. They can copy/paste data locally

**For Reports:**
1. Export as CSV
2. Open in Excel/Google Sheets
3. Create charts/presentations

## 📞 Common Questions

**Q: Is my data secure?**  
A: Yes! Token only accessed when you save. Data stored locally on your device.

**Q: Can I use on mobile?**  
A: Yes! GitHub Pages works on all devices. Touch-friendly interface.

**Q: What if I lose the token?**  
A: Create a new one at [github.com/settings/tokens](https://github.com/settings/tokens). Old one still works until revoked.

**Q: Can multiple people use it?**  
A: Yes! Each person uses their own token. Data saves per month, so collaborate by sharing the repo.

**Q: How do I backup?**  
A: Click "Save Progress to GitHub" or "Export as CSV". Both create downloadable backups.

---

**Need help?** Check the full [SETUP.md](SETUP.md) guide or open an issue in your repo!
