# GitHub Profile Stats Automation

## 📝 Overview
This document explains how the GitHub profile stats are automatically updated to reflect current data (2026 and beyond).

## 🔧 What Was Updated

### 1. **README.md Improvements**
- ✅ Added year indicator "(2026)" to the GitHub Stats section header
- ✅ Added `cache_seconds=86400` parameter to GitHub ReadMe Stats API calls (24-hour cache)
- ✅ Added `date_format` parameters to display full dates including year
- ✅ Added timestamp comment at the end of README for tracking updates

### 2. **GitHub Action Workflow**
Created `.github/workflows/update-readme.yml` to automatically:
- Update the year in the GitHub Stats section header
- Update the "Last updated" timestamp
- Run daily at midnight UTC
- Allow manual triggering from the Actions tab
- Auto-commit changes when the README is updated

## 🚀 How It Works

### Automatic Updates
The GitHub Action workflow runs:
1. **Daily** at 00:00 UTC (scheduled via cron)
2. **On push** to the main branch
3. **Manually** when triggered from the GitHub Actions tab

### What Gets Updated
- The year in "📊 GitHub Stats (YYYY)" automatically updates to current year
- The timestamp comment updates to show when the README was last refreshed
- GitHub stats images refresh due to cache parameters

## 📊 Stats Services Used

The README uses these external services:
1. **GitHub ReadMe Stats** - Shows contribution stats and top languages
2. **GitHub Streak Stats** - Shows contribution streak information
3. **GitHub Profile Trophy** - Shows GitHub achievements

## 🔄 Cache Management

To ensure fresh data:
- `cache_seconds=86400` parameter set (24-hour cache refresh)
- `date_format` parameters added to show full dates with year
- GitHub naturally refreshes these stats periodically

## 🎯 Manual Refresh

To manually trigger an update:
1. Go to your repository's "Actions" tab
2. Click on "Update README Stats" workflow
3. Click "Run workflow" button
4. Select the branch (usually "main")
5. Click "Run workflow"

## 🛠️ Troubleshooting

### Stats Still Showing Old Data?
If stats appear cached:
1. Clear your browser cache
2. Try viewing in an incognito/private window
3. Wait a few hours for external service caches to refresh
4. Manually trigger the GitHub Action

### Workflow Not Running?
Check:
1. Actions are enabled in repository settings
2. Workflow file is in the correct location (`.github/workflows/`)
3. Workflow has proper permissions (contents: write)

## 📚 Additional Resources

- [GitHub ReadMe Stats](https://github.com/anuraghazra/github-readme-stats)
- [GitHub Streak Stats](https://github.com/DenverCoder1/github-readme-streak-stats)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)

## 💡 Tips

1. The workflow commits changes back to your repository, so your commit history will show automated updates
2. You can customize the cron schedule in the workflow file if you want more/less frequent updates
3. The stats services have their own caching mechanisms beyond our control
4. For immediate stats refresh, you can append `?date=$(date +%s)` as a cache-busting parameter manually

---
*Last Updated: 2026-01-31*
