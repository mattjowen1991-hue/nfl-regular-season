## Weekly Workflow

### 📅 Before Sunday (Setup)

#### Step 1: Update the Games

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
  // ... same games
]
```

#### Step 2: Choose the Correct Week Type

| Week Type | When to Use | Points | Full House? |
|-----------|-------------|--------|-------------|
| `'normal'` | Regular weeks 1-17 (except special) | 1 per game | ✅ Yes (+2) |
| `'thanksgiving'` | Week 12.5 (Thanksgiving games only) | 2 per game | ❌ No |
| `'christmas'` | Week 16.5 (Christmas games only) | 2 per game | ❌ No |
| `'week18'` | Final week of regular season | 2 per game | ✅ Yes (+2) |
| `'international'` | Weeks with London/Mexico games | 1 per game* | ✅ Yes (+2) |

*For international weeks, set `doublePoints: true` on the specific international game(s).

#### Step 3: Commit & Push

```bash
git add .
git commit -m "Week 18 setup"
git push
```

#### Step 4: Notify Players

Send a WhatsApp message reminding everyone to submit picks before Sunday 6PM UK.

---

### 🏈 After Games Finish (Sunday Night/Monday)

#### Step 1: Open Admin Dashboard

Go to your admin dashboard URL and log in with PIN: `292292`

#### Step 2: Fetch Live Scores

Click **"🔄 Fetch Live Scores"** - this pulls results from ESPN and auto-selects winners for completed games.

#### Step 3: Review Winners

- ✅ Green border = winner selected
- Check any games that might not have auto-populated
- Manually click to set/change winners if needed

#### Step 4: Save to League Table

1. Click **"💾 Save to League Table"**
2. A modal appears showing:
   - Week number and type
   - All player scores for the week
   - Perfect week points calculation
3. Verify it looks correct
4. Click **"SAVE TO LEAGUE"**

You should see: `✅ Saved to JSONBin successfully!`

#### Step 5: Reset for Next Week

Click **"🔄 Reset for New Week"** → This clears the Picks Bin so players can submit fresh picks.

⚠️ **Only do this AFTER saving scores!**

---

### 📊 Verify Everything Worked

1. Open your League Table (`index.html`)
2. Check the console (F12) for:
   - `✅ Loaded scores from JSONBin`
   - `✅ Schedule updated from ESPN API`
3. Verify player totals are correct
4. Click a player card to check their stats updated

---
