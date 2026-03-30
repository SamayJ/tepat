# Teen Patti Live - Deployment Guide

## 🚀 Quick Deploy Options

### Option 1: Railway (Recommended - Free tier)
1. Push this folder to a GitHub repo
2. Go to [railway.app](https://railway.app) → New Project → Deploy from GitHub
3. Select your repo → Railway auto-detects Node.js
4. Click Deploy → Get your live URL in 2 minutes!

### Option 2: Render (Free tier)
1. Push to GitHub
2. Go to [render.com](https://render.com) → New → Web Service
3. Connect your repo
4. Settings:
   - Build Command: `npm install`
   - Start Command: `npm start`
5. Deploy!

### Option 3: Fly.io
```bash
npm install -g flyctl
flyctl launch
flyctl deploy
```

### Option 4: VPS / DigitalOcean
```bash
# SSH into your server
git clone <your-repo>
cd teenpatti
npm install
# Install PM2 for process management
npm install -g pm2
pm2 start server/index.js --name teenpatti
pm2 save
pm2 startup
```

### Option 5: Local network (play on same WiFi)
```bash
npm install
npm start
# Share your local IP: http://192.168.x.x:3000
```

## 🎮 How to Play

1. **Host** goes to your site → Create Room
2. Set chips, boot amount, max players
3. Copy the link → Share with friends
4. Friends open the link → Enter name → Join
5. Host clicks **Start Game**
6. System deals cards, picks random variation
7. Play blind or see your cards
8. Actions: Blind play | Chaal | Raise | Fold | Show | Sideshow
9. Winner takes the pot, next round starts automatically!

## 🃏 Variations Explained

| Variation | Rule |
|-----------|------|
| Classic | Standard Teen Patti |
| Joker | One random rank is wild |
| AK47 | A, K, 4, 7 are all jokers |
| Muflis | Lowest hand wins |
| 999 | Closest to 9+9+9 total wins |
| Best of Four | 4 cards dealt, best 3 count |

## 🛠 Local Development

```bash
npm install
npm run dev   # uses nodemon for auto-restart
```

Visit http://localhost:3000

## 📁 Project Structure

```
teenpatti/
├── server/
│   ├── index.js          # Express + Socket.io server
│   └── roomManager.js    # Room & game state management
├── shared/
│   └── gameEngine.js     # Card logic, hand evaluation
├── public/
│   ├── index.html        # Single-page app
│   ├── css/style.css     # Complete styling
│   └── js/app.js         # Client-side game logic
├── package.json
└── README.md
```
