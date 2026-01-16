# Team Setup: SAAI Skill Feedback

Quick reference for sharing with your team.

---

## GitHub Repository

**🔗 https://github.com/ServiceNow/skill-feedback**

**Latest Release:** [v1.0.0](https://github.com/ServiceNow/skill-feedback/releases/tag/v1.0.0)

---

## Quick Install (3 Steps)

### 1. Clone the Repository

```bash
git clone https://github.com/ServiceNow/skill-feedback.git
cd skill-feedback/mcp-server
```

### 2. Run Installer

```bash
./install.sh
```

This will:
- Install Node.js dependencies
- Install Python dependencies
- Authenticate with ServiceNow (browser opens)
- Show you the config to add

### 3. Add to Claude Config

Copy the config shown by installer to:

**Claude Desktop:**
```
~/Library/Application Support/Claude/claude_desktop_config.json
```

**Claude Code:**
```
~/.config/claude/config.json
```

**Restart Claude and start using!**

---

## What It Does

Submit feedback about ANY MCP skill directly from Claude:

```
"Report a bug with create-sbo-request"
"Request enhancement - add fuzzy matching"
"Request a new skill for Jira management"
```

Claude will:
- Auto-detect which skill
- Capture conversation context
- Create ServiceNow SBO with details
- Route to David Rider

---

## Documentation Links

- **Installation Guide:** [docs/INSTALL.md](docs/INSTALL.md)
- **User Guide:** [README.md](README.md)
- **Claude Instructions:** [docs/CLAUDE.md](docs/CLAUDE.md)
- **Team Rollout:** [docs/TEAM_MESSAGE.md](docs/TEAM_MESSAGE.md)

---

## Email Template for Team

```
Subject: New Tool - Submit Feedback for Claude Skills

Hi team,

I've created a new Claude skill for submitting feedback about our MCP tools.

🔗 GitHub: https://github.com/ServiceNow/skill-feedback

What it does:
- Report bugs, request enhancements, or propose new skills
- Auto-detects which skill from your conversation
- Creates ServiceNow SBOs with full context

Installation (5 minutes):
1. Clone: git clone https://github.com/ServiceNow/skill-feedback.git
2. Install: cd skill-feedback/mcp-server && ./install.sh
3. Add config to Claude (shown by installer)
4. Restart Claude

Usage:
Just say things like:
- "Report a bug - the dashboard lookup failed"
- "Request enhancement - support date ranges"
- "Request a new skill for Jira"

See docs/INSTALL.md for detailed instructions.

Questions? Let me know!
```

---

## Slack Message Template

```
🆕 New Tool: SAAI Skill Feedback

Submit bugs and feature requests for Claude skills directly from conversations!

📦 GitHub: https://github.com/ServiceNow/skill-feedback
📥 Install: Clone → ./install.sh → Add to config → Restart

✨ Features:
• Auto-detects skill from conversation
• Captures full context automatically
• Creates ServiceNow SBOs
• Works with ANY MCP skill

📖 Full docs: See README.md in repo

Try it: "Request a new skill for [your idea]"
```

---

## Important Notes

### ⚠️ Breaking Change for create-sbo-request Users

The feedback system was removed from create-sbo-request and is now a separate skill.

**What changed:**
- No more `submit_feedback` tool in create-sbo-request
- No more "Provide feedback" prompt after SBO creation
- Feedback functionality moved to standalone skill

**Action needed:**
Install skill-feedback if you want to provide feedback.

**Benefit:**
Now works with ANY skill, not just create-sbo-request!

---

## Testing

After installation, test with:

```
User: "Request a new skill for weather forecasts"
```

Expected response:
```
✓ Thank you for your feedback!
Feedback submitted successfully: DSRT0123456
[ServiceNow link]
```

Check the SBO in ServiceNow to verify details.

---

## Support

**Installation issues:** See [docs/INSTALL.md](docs/INSTALL.md) troubleshooting section

**Questions:** Contact David Rider
- Email: david.rider@servicenow.com
- Slack: @david.rider

**Bugs:** Use the feedback skill itself! (meta)
- Or file GitHub issue: https://github.com/ServiceNow/skill-feedback/issues

---

## Rollout Checklist

For rolling out to your team:

- [ ] Test installation yourself first
- [ ] Update email/Slack templates with your contact info
- [ ] Create distribution channel (email/Slack)
- [ ] Send announcement with GitHub link
- [ ] Schedule optional installation help session
- [ ] Monitor first week for issues
- [ ] Follow up with usage stats after 2 weeks

See [docs/TEAM_MESSAGE.md](docs/TEAM_MESSAGE.md) for detailed rollout guide.

---

## Version History

**v1.0.0** (Jan 16, 2026)
- Initial release
- Bug reports, enhancement requests, new skill requests
- Auto-detection from conversation context
- ServiceNow SBO integration
- Complete documentation

---

## Related Projects

- **create-sbo-request:** https://github.com/ServiceNow/create-sbo-request
  - Create Security BOS tickets in ServiceNow
  - Natural language processing
  - Auto-classification and defaults

---

## License

MIT License - See [LICENSE](LICENSE) file

Free to use, modify, and distribute.