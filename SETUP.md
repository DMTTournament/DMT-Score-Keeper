# 🛠️ Setup Guide

## Prerequisites

- Python 3.8 or higher
- A Discord bot token
- HLL game server RCON credentials (host, port, password)

## Installation

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

4. **Edit `.env` with your settings**

5. **Run the bot:**
   ```bash
   python enhanced_discord_bot.py
   ```

## Environment Variables

### Required

| Variable | Description | Example |
|----------|-------------|---------|
| `DISCORD_TOKEN` | Your Discord bot token | `MTIzNDU2...` |
| `RCON_HOST` | Game server IP address | `123.456.789.012` |
| `RCON_PORT` | RCON port | `7779` |
| `RCON_PASSWORD` | RCON password | `mypassword` |

### Optional

| Variable | Default | Description |
|----------|---------|-------------|
| `RCON_TIMEOUT` | `30` | RCON connection timeout (seconds) |
| `RCON_AUTO_SWITCH` | `true` | Auto-switch on point captures |
| `UPDATE_INTERVAL` | `15` | Discord update frequency (seconds) |
| `ADMIN_ROLE_NAME` | `admin` | Discord role required to control bot |
| `BOT_NAME` | `HLLTankBot` | Name shown in game messages |
| `BOT_AUTHOR` | `YourCommunityName` | Author shown in embed footer |
| `LOG_CHANNEL_ID` | `0` | Discord channel for match logs (0 = disabled) |

## Discord Bot Setup

1. Go to [Discord Developer Portal](https://discord.com/developers/applications)
2. Create a new application and add a bot
3. Copy the bot token into `DISCORD_TOKEN`
4. Invite the bot with `bot` and `applications.commands` scopes
5. Required permissions: Send Messages, Use Slash Commands, Embed Links, Manage Messages
6. Create an "admin" Discord role for users who will control the bot

## RCON Setup

This bot connects directly to your HLL game server using RCON V2. You just need:

- **RCON_HOST** — your server's IP address
- **RCON_PORT** — the RCON port from your server config
- **RCON_PASSWORD** — the RCON password from your server config

No middleware or third-party tools required.

## Troubleshooting

- **Bot won't start:** Check `DISCORD_TOKEN`, `RCON_HOST`, and `RCON_PASSWORD` are set correctly
- **No admin permissions:** Make sure you have the role set in `ADMIN_ROLE_NAME` (default: "admin")
- **RCON not connecting:** Verify host, port, and password. Use `/rcon_status` in Discord to test
- **Auto-switch not working:** Verify `RCON_AUTO_SWITCH=true` and game is on a Warfare map
