# OLYMPUS Live Dashboard

Live multi-agent command center for GitHub Pages.

**URL:** `https://rreidmcg.github.io/olympus-dashboard/`

---

## Features

- 🤖 **Live Agent Status** - See which agents are online/working
- ⏳ **Approval Queue** - Content/expenses waiting for your OK
- 💰 **Financial Health** - Budget tracking in real-time
- 📊 **Project Progress** - Visual progress bars
- 📡 **Activity Feed** - Recent agent actions
- 🔄 **Auto-refresh** - Updates every 30 seconds

---

## Setup Instructions

### Step 1: Create GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Repository name: `olympus-dashboard`
3. Make it **Public**
4. Click **Create repository**

### Step 2: Upload Files

1. Download this folder (`olympus-dashboard`)
2. On your new repo page, click **"uploading an existing file"**
3. Drag and drop all files from this folder
4. Click **Commit changes**

### Step 3: Enable GitHub Pages

1. Go to **Settings** → **Pages** (in your repo)
2. Source: **Deploy from a branch**
3. Branch: **main** / **root**
4. Click **Save**
5. Wait 2-3 minutes
6. Your site will be at: `https://rreidmcg.github.io/olympus-dashboard/`

---

## How Agents Update the Dashboard

Agents write to `data/status.json`. The dashboard polls this file every 30 seconds.

### Manual Update (for testing):

Edit `data/status.json` directly in GitHub:
1. Go to your repo on GitHub
2. Click `data/status.json`
3. Click the **pencil** icon (Edit)
4. Make changes
5. Click **Commit changes**
6. Dashboard updates in ~30 seconds

### Automated Updates (via Zeus):

When agents complete tasks, Zeus can push updates to this repo via Git API.

---

## File Structure

```
olympus-dashboard/
├── index.html          # The dashboard
├── data/
│   └── status.json     # Agent data (edit this to update)
└── README.md           # This file
```

---

## Customization

### Change Colors

Edit the CSS variables in `index.html`:

```css
:root {
    --bg: #0d0d12;        /* Background */
    --green: #00e676;     /* Success/online */
    --yellow: #ffc107;    /* Warning/working */
    --red: #ff5252;       /* Error/danger */
    --cyan: #00d4ff;      /* Accent */
}
```

### Add More Agents

Edit `data/status.json` and add to the `agents` array:

```json
{
  "name": "NewAgent",
  "role": "New Role",
  "status": "idle",
  "currentTask": "Waiting...",
  "nextRun": "2026-03-20T06:00:00Z"
}
```

---

## Troubleshooting

**Dashboard not loading?**
- Make sure GitHub Pages is enabled in Settings
- Check that repo is Public (Private repos need Pro for Pages)
- Wait 2-3 minutes after first commit

**Data not updating?**
- Check browser console (F12) for errors
- Verify `data/status.json` is valid JSON
- Hard refresh: Ctrl+Shift+R (or Cmd+Shift+R on Mac)

**Want faster updates?**
- Edit line 312 in `index.html`: `setInterval(fetchData, 30000);`
- Change `30000` (30s) to `10000` (10s) or `5000` (5s)

---

## Next Steps

1. ✅ Set up GitHub repo
2. ✅ Upload files
3. ✅ Enable GitHub Pages
4. ✅ Bookmark your URL
5. 📱 Add to phone home screen (works like an app)

---

**Questions? Message Zeus.** ⚡
