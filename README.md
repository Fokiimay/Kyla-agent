# Kyla Agent

Skills Marketplace · Hacker Agent · RepoScan

## Quick Deploy to Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/YOUR_USERNAME/kyla-agent)

## Local Development

```bash
git clone https://github.com/YOUR_USERNAME/kyla-agent
cd kyla-agent
npm install

# Setup env vars
cp .env.local.example .env.local
# Edit .env.local with your keys

npm run dev
# → http://localhost:5173
```

## Environment Variables

| Variable | Required | Description |
|---|---|---|
| `VITE_GITHUB_TOKEN` | Optional | GitHub token for RepoScan GraphQL mode (5000 req/hr vs 60) |
| `VITE_LLM_KEY` | Optional | B.ai / Anthropic / OpenAI key for Hacker Agent AI synthesis |
| `VITE_LLM_MODEL` | Optional | `bai` / `claude` / `openai` (default: `bai`) |

### Getting API Keys

**GitHub Token** — `github.com/settings/tokens`
1. Generate new token (classic)
2. Select scope: `public_repo`
3. Copy `ghp_xxxx...`

**B.ai Key** — `chat.b.ai/key`
1. Create API key
2. Copy `sk-z8d9w...`

### Vercel Deployment

1. Push repo to GitHub
2. Import to Vercel
3. Add env vars in **Project Settings → Environment Variables**:
   - `VITE_GITHUB_TOKEN`
   - `VITE_LLM_KEY`
   - `VITE_LLM_MODEL`
4. Deploy

> **Note:** `VITE_` prefix is required for Vite to expose vars to the browser.
> Keys are only sent to their respective API endpoints — never stored server-side.

## Features

- **Skills Marketplace** — 1000+ Claude Code skills from Anthropic, Vercel, Stripe, HashiCorp, Trail of Bits and community
- **Hacker Agent** — Real HTTP probing, security header analysis (Mozilla Observatory), DNS (Cloudflare DoH), 17-path exposure detection, secret scanning, AI synthesis
- **RepoScan** — GitHub repo trust scoring from live API data. GraphQL (1 call with token) or REST fallback. Commit history, community, security signals, 6 dimensions scored out of 100

## Tech Stack

- React 18 + Vite
- D3.js — force network, bubble pack, donut chart, radar chart
- GitHub GraphQL API + REST API
- Mozilla Observatory API (free, no key)
- Cloudflare DNS-over-HTTPS (free, no key)
- Anthropic Claude API / B.ai API / OpenAI API
