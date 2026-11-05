# Using VaultCord

VaultCord protects Discord servers (member backup and restore, verification, alt/VPN blocking,
anti-spam). These instructions explain how to use the VaultCord MCP tools safely.

## Start every session the same way
1. Call `whoami` to confirm which VaultCord account is signed in.
2. Call `list_servers` and match the server the user means by **name**, then use its ID.
   If more than one server could match, ask which one. Never guess a server ID.

## What the tools do
| Area | Tools |
|---|---|
| Account | `whoami`, `get_subscription_status`, `export_account_data`, `create_api_key` |
| Servers | `list_servers`, `get_server`, `add_server`, `update_server_settings`, `set_verify_message_template`, `set_log_message_template` |
| Members | `get_member`, `approve_member`, `ban_member`, `list_rejected_members`, `approve_rejected_members`, `list_unauthorized_members`, `remove_unauthorized_members` |
| Allow / block lists | `list_allowlist`, `allow_entry`, `unallow_entry`, `list_blocklist`, `block_entry`, `unblock_entry` |
| Backups | `list_backups`, `create_backup`, `schedule_backup`, `list_scheduled_backups`, `restore_backup`, `delete_backup`, `restore_server` |
| Custom bots | `list_bots`, `get_bot`, `add_bot`, `get_bot_invite_link`, `delete_bot` |
| Member pulls & orders | `list_pull_history`, `pull_members`, `request_member_transfer`, `track_order`, `restart_order` |
| Marketplace | `list_marketplace_sellers`, `get_marketplace_balance`, `buy_members`, `request_marketplace_refund` |
| Docs | `search`, `execute` |

## Safety rules (always follow)
- **Read first, then act.** Before changing anything, show the user the current state
  (for example `get_server` before `update_server_settings`, `list_backups` before a restore).
- **Ask for explicit confirmation** before any of these, and repeat back exactly what will happen
  and to which server: `ban_member`, `remove_unauthorized_members`, `restore_backup`,
  `restore_server`, `delete_backup`, `delete_bot`, `pull_members`, `request_member_transfer`,
  `buy_members`, `request_marketplace_refund`, `cancel_subscription`, `request_server_deletion`.
- **Two-step confirmations belong to the user.** `confirm_server_deletion`,
  `confirm_account_deletion` and `confirm_email_change` must only be called with a code the
  user has typed themselves in this conversation. Never reuse, invent or guess a code.
- Anything that spends money (`buy_members`) needs the user to state the amount and quantity.
- `create_api_key` returns a secret once. Tell the user to store it safely and do not repeat it
  later in the conversation.
- If a tool returns 401/403, the user needs to reconnect VaultCord (sign in again).

## Good first prompts
- "Show me my VaultCord servers and their verification status."
- "Back up my main server now and schedule a daily backup."
- "Who was rejected from verification in the last day, and why?"
- "Block this IP / user ID from verifying on my server."

More help: https://docs.vaultcord.com
