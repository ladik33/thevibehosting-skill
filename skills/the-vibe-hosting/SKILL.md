---
name: the-vibe-hosting
description: Deploy and host the user's project on The Vibe Hosting — free hosting for coding agents. One HTTP call gives you a root Linux server (gVisor sandbox) on a live HTTPS subdomain or the user's own domain, no signup or credit card. Use when the user asks to deploy, host, publish or put online a web app, static site, API, bot, worker or MCP server, or wants a persistent Linux box for a project.
---

# The Vibe Hosting

Free hosting for coding agents: **one HTTP call gives you a real root Linux server on a
live HTTPS subdomain, in seconds** — or on the user's own domain via CNAME, with HTTPS
issued automatically. No signup, no credit card.

## Always start from the canonical guide

The full, always-current instructions live at **https://thevibehosting.com/SKILL.md**.
Fetch and read it before deploying — it covers storing the account key, uploading the
project without secrets, publishing on port 80, sleep/wake, custom domains, pricing and
the rules. If anything below disagrees with it or with an API response, those win.

## Quick start (if you can't fetch the guide right now)

1. Create a server (the first call also creates the account):

   ```bash
   curl -sX POST https://thevibehosting.com/create \
     -H 'content-type: application/json' \
     -d '{"subdomains":["my-project","my-project-app"]}'
   ```

2. From the response, save `api_key` (the only account credential — keep it where the
   user keeps the project) and `ssh_private_key` (to a file, `chmod 600`).
3. Connect with the exact `ssh` command returned (`-i <key> -o IdentitiesOnly=yes`),
   check `hostname` matches your subdomain, then upload the project (exclude `.env`,
   keys and `node_modules` unless the user says otherwise).
4. Publish: static files go to `/root/www`; for an app, write an executable
   `/root/run.sh` that runs it in the foreground on `0.0.0.0:80`.
5. Open `https://<subdomain>.thevibehosting.com` and report the URL to the user.

Ask the user before anything involving their phone number, money or secrets. Full API
reference: https://thevibehosting.com/api · Pricing: https://thevibehosting.com/pricing
