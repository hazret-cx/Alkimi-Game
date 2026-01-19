# Fee Dodger 🎮

An addictive endless runner game for Alkimi Exchange. Navigate your ad dollar through the programmatic supply chain - dodge the fees, keep your budget!

## 🎯 Game Mechanics

- **Swipe/Tap** to move your ad dollar left and right
- **Dodge** fee collectors (SSPs, DSPs, Data Taxes, Hidden Margins)
- **Collect** bonus stars for extra points
- **Build streaks** for score multipliers (5 dodges = 2x, 10 dodges = 3x)

## 📊 Scoring

```
Final Score = Base Score × Budget Multiplier × Combo Bonus
```

- **Distance**: 1 point per frame survived
- **Budget Retained**: Starts at $100, each hit costs $6-15
- **Combo Streak**: Consecutive dodges build multipliers

## 🚀 Deploy to Netlify

### Option 1: Drag & Drop (Fastest)
1. Go to [netlify.com/drop](https://app.netlify.com/drop)
2. Drag the entire `fee-dodger` folder onto the page
3. Done! You'll get a live URL instantly

### Option 2: GitHub + Netlify (Recommended for updates)
1. Push this folder to a GitHub repo
2. Log into Netlify → "Add new site" → "Import an existing project"
3. Connect your GitHub repo
4. Deploy settings:
   - **Build command**: (leave blank)
   - **Publish directory**: `/` or `.`
5. Click "Deploy site"

### Option 3: Netlify CLI
```bash
npm install -g netlify-cli
netlify login
netlify deploy --prod --dir=.
```

## 🎨 Customisation

### Change Colors (Alkimi Branding)
Edit the CSS variables at the top of `index.html`:
```css
:root {
    --alkimi-green: #00D4AA;
    --alkimi-dark: #0A1628;
    --alkimi-darker: #060D18;
    /* ... */
}
```

### Adjust Difficulty
In the JavaScript, modify:
```javascript
game.speed = 3;        // Starting speed (higher = faster)
game.spawnRate = 1500; // Milliseconds between obstacles (lower = more obstacles)
```

### Add/Modify Obstacles
Edit the `obstacleTypes` array:
```javascript
const obstacleTypes = [
    { type: 'ssp', name: 'SSP Fee', icon: '🏢', fee: 8 },
    { type: 'dsp', name: 'DSP Fee', icon: '🖥️', fee: 10 },
    // Add your own...
];
```

## 📱 QR Code Setup

1. Deploy to Netlify (get your URL like `fee-dodger.netlify.app`)
2. Generate QR code at [qr-code-generator.com](https://www.qr-code-generator.com/)
3. Download and add to your event materials

## 🏆 Leaderboard

The game uses `localStorage` for the leaderboard, meaning:
- ✅ Works instantly, no backend needed
- ✅ Persists on each device
- ⚠️ Each device has its own leaderboard

### Want a Shared Leaderboard?
For events where everyone competes on one board, you have options:

1. **Supabase** (Free tier, easy): Add a few lines of code to POST scores to Supabase
2. **Google Sheets**: Use Sheets API as a simple database
3. **Display device**: Have one tablet showing the leaderboard that people manually update

Let me know if you want me to add Supabase integration!

## 📄 License

Built for Alkimi Exchange. Feel free to customise for your events and campaigns.
