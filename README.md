# The Vibe Hosting — agent skill

Free hosting for coding agents: one HTTP call gives your agent a root Linux server
(gVisor sandbox) on an HTTPS subdomain — or your own domain — with no signup or credit
card.

## Install

```bash
npx skills add ladik33/thevibehosting-skill
```

Works with Claude Code, Cursor, Codex and other agents that support Agent Skills.
Then just ask your agent to deploy or host your project.

## No install needed

Agents can also use the service directly — say this to your agent:

```text
Read https://thevibehosting.com/SKILL.md and follow the instructions to deploy your project.
```

## Links

- Website: https://thevibehosting.com
- Canonical agent guide: https://thevibehosting.com/SKILL.md
- API reference: https://thevibehosting.com/api
- Pricing: https://thevibehosting.com/pricing

The skill in this repository is a thin entry point that points the agent to the
canonical guide, so it never goes stale. The hosting service itself is closed-source.
Operated by [@LadaHrbacek](https://x.com/LadaHrbacek) · hello@thevibehosting.com

License: MIT (this repository only).
