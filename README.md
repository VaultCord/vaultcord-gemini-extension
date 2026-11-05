# VaultCord — Gemini CLI extension

VaultCord connects your AI assistant to your [VaultCord](https://vaultcord.com) account so it can
manage your protected Discord servers: servers and settings, verification, members,
allow/block lists, backups and restores, custom bots, and orders.

- **Server:** `https://ai.vaultcord.com/mcp` (Streamable HTTP)
- **Auth:** OAuth 2.0 with dynamic client registration. No API key or client ID needed. You sign
  in to VaultCord the first time a tool is used.
- **Permissions:** every call runs with your own VaultCord permissions.
- **Docs:** https://docs.vaultcord.com · **Privacy:** https://vaultcord.com/privacy-policy · **Terms:** https://vaultcord.com/terms-of-service · **Support:** abuse@vaultcord.com

## Install
```bash
gemini extensions install https://github.com/VaultCord/vaultcord-gemini-extension
```
Restart Gemini CLI, then run `/mcp auth vaultcord` and sign in.
