# NovaMind Workspace on Vercel

This folder is the Vercel deployment root. It contains the static NovaMind app and one secure server-side endpoint:

- `POST /api/nova/organize` — turns an Inbox capture into a suggested destination. It never changes user data by itself.

## Deploy

1. Create a new GitHub repository and upload the contents of this folder.
2. Import that repository into Vercel.
3. In Vercel, open **Project → Settings → Environment Variables**.
4. Add `DEEPSEEK_API_KEY` with your real DeepSeek API key.
5. Optionally add `DEEPSEEK_MODEL` (the default is `deepseek-chat`).
6. Deploy.

Never put the real key in `index.html`, a committed `.env` file, or GitHub.

## Local testing

Install the Vercel CLI, then run:

```bash
npm install -g vercel
vercel dev
```

Create a local `.env.local` file from `.env.example` and place your real key only in `.env.local`. It is ignored by Git.

## Current limitation

This is a prototype endpoint. It includes input validation and keeps the key server-side, but production should add authenticated users, per-user rate limiting, abuse monitoring, and persistent user data.
