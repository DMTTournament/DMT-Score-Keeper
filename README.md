# 🎯 HLL Tank Overwatch Discord Bot

A Discord bot for Hell Let Loose communities that tracks time control of the center point during tank matches and calculates DMT scores.

![Discord](https://img.shields.io/badge/Discord-Bot-7289da?style=flat-square&logo=discord)
![Python](https://img.shields.io/badge/Python-3.8+-3776ab?style=flat-square&logo=python)
![Railway](https://img.shields.io/badge/Deploy-Railway-0B0D0E?style=flat-square&logo=railway)

## ✨ Features

- **⏱️ Time Control Tracking** - Tracks how long each team controls the center point
- **🤖 Auto-Detection** - Automatically switches when points are captured via direct RCON V2
- **🎮 Live Game Integration** - Shows current map, players, and game time
- **📊 DMT Scoring** - Full DMT score calculation including combat, cap time, first cap bonus, and held mid bonus
- **🏆 Match Results** - Automatic results posting when matches end
- **⚔️ In-Game Messages** - Notifications sent to all players with current scores

## 🖼️ Preview

The bot creates interactive Discord embeds showing:
- Current map and player count
- Control time for both Allies and Axis
- Who's currently defending/attacking
- Time advantages and match leader
- Live DMT scores with full breakdown
- Live game time remaining

## 🏆 DMT Scoring

**DMT Total = Combat Score + Cap Score + First Cap Bonus + Held Mid Bonus**

- **Combat Score** = 3 × (Crew 1 High + Crew 2 High + Crew 3 High + Crew 4 High + Commander P-Strike)
- **Cap Score** = 0.5 × center point cap seconds
- **First Cap Bonus** = +285 points to team that captured first
- **Held Mid Bonus** = +285 points to team holding mid at match end

## 🚀 Quick Deploy to Railway

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/new/template?template=https://github.com/StoneyRebel/HLL-Tank-Overwatch)

### Railway Deployment Steps:

1. **Click the Railway deploy button above** (or follow manual steps below)

2. **Set Environment Variables in Railway:**
   ```
   DISCORD_TOKEN=your_discord_bot_token
   RCON_HOST=your_game_server_ip
   RCON_PORT=your_rcon_port
   RCON_PASSWORD=your_rcon_password
   ```

3. **Deploy!** Railway will automatically build and start your bot.

### Manual Railway Setup:

1. **Fork this repository** to your GitHub account

2. **Create a new Railway project:**
   - Go to [Railway](https://railway.app)
   - Click "New Project"
   - Select "Deploy from GitHub repo"
   - Choose your forked repository

3. **Add Environment Variables:**
   - In Railway dashboard, go to your project
   - Click "Variables" tab
   - Add the required variables (see [Environment Variables](#-environment-variables) below)

4. **Deploy:**
   - Railway will automatically detect Python and deploy
   - Check the deployment logs for any errors

## 🛠️ Local Development Setup

### Prerequisites
- Python 3.8 or higher
- A Discord bot token
- HLL game server RCON credentials (host, port, password)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/StoneyRebel/HLL-Tank-Overwatch.git
   cd HLL-Tank-Overwatch
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Create environment file:**
   ```bash
   cp .env.template .env
   ```

4. **Edit `.env` with your settings:**
   ```bash
   nano .env
   ```

5. **Run the bot:**
   ```bash
   python enhanced_discord_bot.py
   ```

## ⚙️ Environment Variables

### Required Variables

| Variable | Description | Where to Get |
|----------|-------------|--------------|
| `DISCORD_TOKEN` | Your Discord bot token | [Discord Developer Portal](https://discord.com/developers/applications) |
| `RCON_HOST` | Game server IP address | Your server provider |
| `RCON_PORT` | RCON port | Your server provider |
| `RCON_PASSWORD` | RCON password | Your server provider |

### Optional Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `RCON_TIMEOUT` | `30` | RCON connection timeout (seconds) |
| `RCON_AUTO_SWITCH` | `true` | Auto-switch on point captures |
| `UPDATE_INTERVAL` | `15` | Discord update frequency (seconds) |
| `ADMIN_ROLE_NAME` | `admin` | Discord role required to control bot |
| `BOT_NAME` | `HLLTankBot` | Name shown in game messages |
| `BOT_AUTHOR` | `YourCommunityName` | Author shown in embed footer |
| `LOG_CHANNEL_ID` | `0` | Discord channel for match logs (0 = disabled) |

## 🎮 Discord Setup

### 1. Create Discord Application

1. Go to [Discord Developer Portal](https://discord.com/developers/applications)
2. Click "New Application"
3. Give it a name like "HLL Tank Overwatch"

### 2. Create Bot

1. Go to the "Bot" section
2. Click "Add Bot"
3. Copy the token for your `.env` file

### 3. Set Permissions

1. In "OAuth2" → "URL Generator"
2. Select "bot" and "applications.commands"
3. Select permissions:
   - Send Messages
   - Use Slash Commands
   - Embed Links
   - Manage Messages
4. Use the generated URL to invite bot to your server

### 4. Create Admin Role

Create a Discord role named "admin" (or customize with `ADMIN_ROLE_NAME`) and assign it to users who should control the bot.

## 📖 Usage

### Starting a Match

1. Use `/reverse_clock` in any Discord channel
2. Click "▶️ Start Match" to begin
3. The bot connects directly to your HLL game server via RCON V2 and starts tracking

### Controlling the Clock

- **Manual Control:** Use "Allies" and "Axis" buttons to manually switch
- **Auto Control:** Toggle "🤖 Auto" for automatic switching on point captures
- **View Stats:** Click "📊 Stats" for detailed information
- **Stop Match:** Click "⏹️ Stop" to end and show final DMT results

### Commands

| Command | Description |
|---------|-------------|
| `/reverse_clock` | Create a new match clock |
| `/rcon_status` | Check RCON connection status |
| `/server_info` | Get current server information |
| `/send_message` | Send message to all players in game (admin only) |
| `/help_clock` | Show help information |

## 🔗 RCON V2 Connection

This bot connects **directly** to your Hell Let Loose game server using the RCON V2 protocol — no middleware required. It uses:

- **TCP connection** to your server's RCON port
- **XOR encryption** with a session key
- **JSON-based commands** for all game data

All you need is the server IP, RCON port, and RCON password.

## 🐛 Troubleshooting

### Common Issues

**Bot won't start:**
- Check `DISCORD_TOKEN`, `RCON_HOST`, and `RCON_PASSWORD` in environment variables

**No admin permissions:**
- Ensure you have the role specified in `ADMIN_ROLE_NAME`
- Default role name is "admin"

**RCON not connecting:**
- Verify `RCON_HOST` and `RCON_PORT` are correct
- Check `RCON_PASSWORD` is valid
- Ensure the game server is running

**Auto-switch not working:**
- Verify `RCON_AUTO_SWITCH=true`
- Check game is on a Warfare map

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built for the Hell Let Loose tank community
- Direct HLL RCON V2 integration
- Designed for competitive tank-focused gameplay

## 📞 Support

- **Issues:** [GitHub Issues](https://github.com/StoneyRebel/HLL-Tank-Overwatch/issues)

---

**Made with ❤️ for the HLL Tank Community**
