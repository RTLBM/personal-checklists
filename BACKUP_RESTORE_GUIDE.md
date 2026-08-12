# Backup & Restore Feature Guide

## Why Your Data Was Lost

Your checklist app uses **localStorage** (through jStorage), which persists data in the browser but is **not permanent**. It can be cleared by:

- 📱 **Phone restart** - Mobile browsers may clear cache on restart
- 🧹 **Clearing app data/cache** - Intentional or automatic clearing
- 🔄 **Browser updates** - Some browser versions auto-clear old storage
- 💾 **Low storage** - System may clear browser cache if storage is full
- 🔐 **Private/Incognito mode** - Data isn't saved in private browsing
- 🌐 **Browser cache settings** - Some browsers auto-clear cache periodically

## Solution: Download & Restore Backups

The updated version now includes **Download** and **Import** buttons in the menu (three dots menu).

### How to Use

#### 1. **Download a Backup**
   - Click the **⋮ (three dots)** menu in the top navigation
   - Click **"Download Backup"**
   - A JSON file will be downloaded to your device with the name format: `lotf-checklist-backup-YYYY-MM-DD.json`
   - **Store this file safely** - keep it in cloud storage or email it to yourself

#### 2. **Restore from Backup**
   - Click the **⋮ (three dots)** menu
   - Click **"Import Backup"**
   - Select the JSON backup file from your device
   - Confirm when prompted
   - Your profiles and checklist progress will be restored instantly

### Best Practices

✅ **Download regularly:**
   - After a gaming session
   - Before your phone storage is full
   - Before major phone updates
   - Before clearing app data

✅ **Keep multiple backups:**
   - Download one weekly
   - Store in Google Drive, OneDrive, or email
   - Name them with dates for easy reference

✅ **Test restoration:**
   - Try importing a backup once to confirm it works
   - Don't panic if you need to restore - your data is safe!

### What Gets Backed Up

The backup file includes:
- ✓ All profiles you've created
- ✓ All checked/uncompleted items
- ✓ Collapse/expand states of sections
- ✓ Filter settings (show/hide completed, equipment)
- ✓ Currently selected profile

### File Format

The backup is a simple JSON file. You can open it in any text editor to view your progress, though it's not meant to be manually edited.

Example structure:
```json
{
  "timestamp": "2024-01-15T10:30:00Z",
  "currentProfile": "Default Profile",
  "profiles": {
    "Default Profile": {
      "checklistData": {
        "item_1": true,
        "item_2": false,
        ...
      },
      "collapsed": {...},
      "filters": {...}
    }
  }
}
```

### Troubleshooting

**"Invalid backup file format" error:**
- Make sure you're using a file downloaded from this app
- Don't rename or modify the .json file manually

**Import succeeded but data looks wrong:**
- Try refreshing the page (F5 or ⟳)
- Check if the correct profile is selected

**Can't find the backup file:**
- Check your device's Downloads folder
- On mobile, it may be in the Files app or Documents folder

---

## Long-term Data Persistence

For ultimate reliability, consider these options:

1. **Cloud Storage Integration** - Store backups in Google Drive/OneDrive automatically
2. **IndexedDB** - A more powerful browser storage (bigger limit)
3. **Server Sync** - Save progress to a remote server (requires backend)

For now, **regular manual backups** (weekly) will keep your progress safe!
