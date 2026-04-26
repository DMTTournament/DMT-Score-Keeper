# 🚂 Railway Deployment Guide

This guide will help you deploy the HLL Tank Overwatch Bot to Railway in just a few minutes.

## 🎯 Why Railway?

- **Free tier available** - Perfect for small communities
- **Auto-scaling** - Handles traffic spikes automatically  
- **Easy deployment** - Deploy directly from GitHub
- **24/7 uptime** - Your bot stays online
- **Simple configuration** - Environment variables through web interface

## 🚀 Quick Deploy (Recommended)

### Option 1: One-Click Deploy
1. Click this button: [![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/new/template?template=https://github.com/StoneyRebel/HLL-Tank-Overwatch)
2. Connect your GitHub account
3. Set your environment variables (see below)
4. Click "Deploy"

### Option 2: Manual Deploy

#### Step 1: Prepare Your Repository
1. **Fork this repository** to your GitHub account
2. **Clone your fork locally** (optional, for customization)

#### Step 2: Create Railway Project
1. Go to [Railway.app](https://railway.app)
2. Sign in with GitHub
3. Click "New Project"
4. Select "Deploy from GitHub repo"
5. Choose your forked repository

#### Step 3: Configure Environment Variables
In Railway dashboard, go to your project and click "Variables":

**Required Variables:**
```
DISCORD_TOKEN=your_discord_bot_token_here
RCON_HOST=your_game_server_ip
RCON_PORT=your_rcon_port
RCON_PASSWORD=your_rcon_password
```

**Recommended Variables:**
```
BOT_AUTHOR=YourCommunityName
ADMIN_ROLE_NAME=admin
```

#### Step 4: Deploy
Railway will automatically build and deploy your bot!

## ⚙️ Environment Variables Setup

### Getting Your Discord Token

1. **Go to [Discord Developer Portal](https://discord.com/developers/applications)**
2. **Create New Application** or select existing one
3. **Go to "Bot" section**
4. **Copy the Token**
5. **Add to Railway as `DISCORD_TOKEN`**

### Getting Your RCON Credentials

Your RCON credentials come from your game server provider:
- **RCON_HOST** — the server IP address
- **RCON_PORT** — the RCON port (check your server control panel)
- **RCON_PASSWORD** — the RCON password set in your server config

## 🔧 Complete Variable Reference

| Variable | Required | Example | Description |
|----------|----------|---------|-------------|
| `DISCORD_TOKEN` | ✅ | `MTIzNDU2...` | Your Discord bot token |
| `RCON_HOST` | ✅ | `123.456.789.012` | Game server IP address |
| `RCON_PORT` | ✅ | `7779` | RCON port |
| `RCON_PASSWORD` | ✅ | `mypassword` | RCON password |
| `BOT_AUTHOR` | ❌ | `MyTankClan` | Name shown in bot footer |
| `ADMIN_ROLE_NAME` | ❌ | `admin` | Discord role required to control bot |
| `RCON_AUTO_SWITCH` | ❌ | `true` | Auto-switch on point captures |
| `UPDATE_INTERVAL` | ❌ | `15` | Update frequency in seconds |
| `LOG_CHANNEL_ID` | ❌ | `123456789` | Discord channel ID for match logs |

## 🔍 Troubleshooting Railway Deployment

### Common Issues

**❌ Build Failed**
- Check that `requirements.txt` is present
- Verify Python syntax in your code
- Look at Railway build logs for specific errors

**❌ Bot Starts But Doesn't Respond**
- Verify `DISCORD_TOKEN` is correct and valid
- Check bot permissions in Discord server
- Ensure bot is invited to your server with correct permissions

**❌ RCON Connection Failed**
- Verify `RCON_HOST` and `RCON_PORT` are correct
- Check `RCON_PASSWORD` is valid
- Ensure the game server is running
- Use `/rcon_status` in Discord to test the connection

**❌ Permission Denied**
- Make sure you have the `ADMIN_ROLE_NAME` role in Discord
- Default role name is "admin" (case-insensitive)

### Checking Logs

1. **Go to Railway dashboard**
2. **Click on your project**
3. **Click "Deployments" tab**
4. **Click on latest deployment**
5. **View logs for errors**

### Testing Your Deployment

1. **Check bot status:** Bot should show as "Online" in Discord
2. **Test connection:** Use `/rcon_status` command
3. **Test clock:** Use `/reverse_clock` command
4. **Test RCON:** Click "🔗 Test RCON" button

## 💰 Railway Pricing

### Free Tier
- **$5 free credit** per month
- **500 hours** of usage
- Perfect for small communities

### Pro Plan
- **$20/month** for unlimited usage
- Priority support
- Better performance

### Estimated Costs
- **Small community (24/7):** ~$3-5/month
- **Large community (24/7):** ~$8-12/month

## 🔄 Updating Your Bot

### Automatic Updates (Recommended)
1. **Enable auto-deploy** in Railway dashboard
2. **Pull updates** to your forked repository
3. **Railway automatically deploys** changes

### Manual Updates
1. **Pull latest changes** to your fork
2. **Push to your repository**
3. **Railway redeploys** automatically

## 📊 Monitoring

### Railway Dashboard
- **View real-time logs**
- **Monitor resource usage**
- **Track deployment history**
- **Set up alerts**

### Bot Health Checks
- Use `/rcon_status` to check RCON connection
- Monitor Discord for bot responsiveness
- Check Railway logs for errors

## 🆘 Getting Help

### Railway Support
- [Railway Documentation](https://docs.railway.app)
- [Railway Discord](https://discord.gg/railway)

### Bot Support
- **GitHub Issues:** [Report bugs here](https://github.com/StoneyRebel/HLL-Tank-Overwatch/issues)
- **Documentation:** Check README.md and SETUP.md

## 🎉 Success!

Once deployed, your bot should:
- ✅ Show as "Online" in Discord
- ✅ Respond to `/reverse_clock` command
- ✅ Connect to your HLL game server via RCON V2
- ✅ Track tank battle control times and DMT scores
- ✅ Send notifications to players in game

**Your HLL Tank Overwatch Bot is now live! 🎯**

---

**Need help?** Create a GitHub issue!
