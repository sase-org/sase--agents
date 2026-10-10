- **PLAN:**
  [202610/telegram_notification_suppression.md](https://github.com/sase-org/sase--plans/blob/main/202610/telegram_notification_suppression.md)
- **AGENTS:**
  - [bbugyi200.athena.0zg--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zg.md)

We need a notification configuration rule/action to suppress Telegram notifications. I
know we already have a notification rules config, but am not sure if we have a way to
suppress Telegram notifications specifically. Can you help me implement this, if it
doesn't already exist, and start disabling task bead notifications from triggering
Telegram notifications by modifying the sase_athena.yml file in my chezmoi repo? I
receive way too many of these Telegram notifications currently and already suppress task
bead notifications in the TUI.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
