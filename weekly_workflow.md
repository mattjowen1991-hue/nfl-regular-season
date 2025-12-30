# Weekly Workflow

## 📅 Before Sunday (Setup)

### Step 1: Update the Games

Edit **both** `player-picks.html` and `admin-dashboard-v2.html`:

```javascript
// player-picks.html CONFIG:
WEEK: 18,
DEADLINE: '2026-01-11T18:00:00',  // Next Sunday 6PM UK
GAMES: [
  { home: 'Team A', away: 'Team B', doublePoints: false },
  { home: 'Team C', away: 'Team D', doublePoints: false },
  // ... all games for the week
]

// admin-dashboard-v2.html CONFIG:
WEEK: 18,
WEEK_TYPE: 'week18',  // See week types below
GAMES: [
  { home: 'Team A', away: 'Team B', doublePoints: false },
  { home: 'Team C', away: 'Team D', doublePoints: false },
  // ... same games - MUST MATCH!
]
```

### Step 2: Choose the Correct Week Type

| Week Type | When to Use | Points | Full House? |
|-----------|-------------|--------|-------------|
| `'normal'` | Regular weeks 1-17 (except special) | 1 per game | ✅ Yes (+2) |
| `'thanksgiving'` | Week 12.5 (Thanksgiving games only) | 2 per game | ❌ No |
| `'christmas'` | Week 16.5 (Christmas games only) | 2 per game | ❌ No |
| `'week18'` | Final week of regular season | 2 per game | ✅ Yes (+2) |
| `'international'` | Weeks with London/Mexico games | 1 per game* | ✅ Yes (+2) |

*For international weeks, set `doublePoints: true` on the specific international game(s).

### Step 3: Commit & Push

```bash
git add .
git commit -m "Week 18 setup"
git push
```

### Step 4: Notify Players

Send a WhatsApp message reminding everyone to submit picks before Sunday 6PM UK.

---

## 🏈 After Games Finish (Sunday Night/Monday)

### Step 1: Open Admin Dashboard

Go to your admin dashboard URL and log in with PIN: `292292`

### Step 2: Check Status Indicators

The header shows two connection status indicators:
- **JSONBin** - Should turn green when picks data loads
- **ESPN Scores API** - Will turn green when you fetch scores

### Step 3: Fetch Live Scores

Click **"🔄 Fetch Live Scores"** - this pulls results from ESPN and auto-selects winners for completed games.

Check both status indicators in the header turn green:
- **JSONBin** - should already be green from loading picks
- **ESPN Scores API** - turns green after successful fetch

### Step 4: Review Winners

- ✅ Green border = winner selected
- Check any games that might not have auto-populated
- Manually click to set/change winners if needed
- Use the dropdown menus to manually select winners if ESPN didn't auto-detect

### Step 5: Save to League Table

1. Click **"💾 Save to League Table"**
2. A modal appears showing:
   - Week number and type
   - All player scores for the week
   - Perfect week points calculation
3. Verify it looks correct
4. Click **"SAVE TO LEAGUE"**

You should see:
- `✅ Saved successfully!` in the modal
- Console shows: `✅ Picks history saved`

**What this saves:**
- Scores to the Scores Bin
- Perfect week points to config
- Detailed picks to the Picks History Bin

### Step 6: Reset for Next Week

Click **"🔄 Reset for New Week"** → This clears the Picks Bin so players can submit fresh picks.

⚠️ **Only do this AFTER saving scores!**

---

## 📊 Verify Everything Worked

1. Open your League Table (`index.html`)
2. Check the console (F12) for:
   - `✅ Loaded scores from JSONBin`
   - `✅ Loaded picks history from JSONBin`
   - `✅ Schedule updated from ESPN API`
3. Verify player totals are correct
4. Click a player card to check their stats updated

---

## ✅ Quick Checklist

```
BEFORE GAMES:
□ Update WEEK number in both files
□ Update DEADLINE date in player-picks.html
□ Update GAMES array in both files (must match!)
□ Set correct WEEK_TYPE in admin dashboard
□ Commit and push changes
□ Notify players

AFTER GAMES:
□ Open Admin Dashboard
□ Check JSONBin status indicator is green
□ Fetch Live Scores
□ Check ESPN status indicator is green
□ Verify winners are correct
□ Save to League Table
□ Check console for "✅ Picks history saved"
□ Reset for New Week
□ Verify on League Table
```
