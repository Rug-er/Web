# Discord Bot Control Panel

A Discord bot bundled with a **web control panel**. Edit your bot's information in
the browser, hit **Save**, and the bot updates its systems **live** — no restart
needed.

![panel](docs/panel.png)

## What you can edit from the website

- **Identity & presence** — display name, online status (online / idle / dnd /
  invisible), and activity (Playing / Listening / Watching / Competing /
  Streaming + text). Changes apply to the bot's Discord presence instantly.
- **Commands** — custom `prefix` + a list of trigger → response commands you can
  add, edit, enable/disable, or remove. Responses support placeholders
  `{user}`, `{username}`, `{server}`. A built-in `help` command lists them.
- **Welcome messages** — greet new members in a channel of your choice.

Everything is stored in a local SQLite database (`data/panel.db`) that both the
web server and the bot share, so they never drift out of sync.

## How "auto-update" works

The bot and the web server run in the **same process** and share an in-memory
event bus. When you save settings via the dashboard, a `config update` event
fires and the bot immediately re-applies its presence and reloads commands.
There's nothing to redeploy or restart.

```
Browser ──POST /api/settings──▶ Express ──saveSettings()──▶ SQLite
                                              │
                                              └─emit("update")─▶ Bot re-applies presence + commands
```

## Setup

1. **Create a bot** at https://discord.com/developers/applications
   - Add a **Bot**, then under *Privileged Gateway Intents* enable
     **Message Content Intent** and **Server Members Intent**.
   - Copy the bot token.
   - Invite the bot to your server (OAuth2 → URL Generator → scopes `bot`,
     permissions: Send Messages / View Channels).

2. **Configure**
   ```bash
   cp .env.example .env
   # paste your token into DISCORD_TOKEN
   ```

3. **Install & run**
   ```bash
   npm install
   npm start
   ```

4. Open the panel at **http://localhost:3000**, edit, and Save.

> The control panel runs even without a token — you just won't see the bot come
> online until `DISCORD_TOKEN` is set.

## Scripts

| Command         | Description                              |
| --------------- | ---------------------------------------- |
| `npm start`     | Run the bot + control panel              |
| `npm run dev`   | Same, with auto-reload on file changes   |
| `npm run lint`  | Lint the source                          |

## Project structure

```
src/
  config.js   SQLite store + event bus (single source of truth)
  bot.js      discord.js client; applies config live
  server.js   Express API + serves the dashboard
  index.js    wires bot + server together
  public/     the dashboard (HTML/CSS/JS, no build step)
```
