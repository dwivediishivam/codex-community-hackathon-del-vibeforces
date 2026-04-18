# Setup

## Stack

- `frontend/`: Next.js App Router, Tailwind CSS v4, shadcn/base-ui, Monaco, Framer Motion
- `backend/`: Express + TypeScript + OpenAI SDK + Puppeteer
- `shared/`: challenge definitions, seed data, shared types
- `supabase/`: SQL migrations and generated seed SQL

## What Ships In This Repo

- 30 challenges across spec-to-prompt, token golf, bug fix, architecture pick, and UI reproduction
- learner, recruiter, and admin surfaces
- public recruiter test links and contest pages
- Supabase auth/profile/test/contest/submission flows
- generated voice-note assets, UI screenshots, and brand assets
- seeded leaderboard, contest, and recruiter test data

## Local Setup

1. Copy `.env.example` to `.env` and fill in the Supabase/OpenAI values.
2. Install dependencies:

```bash
npm install
npm --prefix frontend install
npm --prefix backend install
```

3. Generate local assets:

```bash
npm run assets:generate
```

4. Apply database migrations and seed demo data:

```bash
npm run db:migrate
npm run db:seed
```

5. Start the app:

```bash
npm run dev
```

Frontend runs on `http://localhost:3000`. Backend runs on `http://localhost:3001`.

## Useful Scripts

- `npm run dev`
- `npm run build`
- `npm run typecheck`
- `npm run assets:generate`
- `npm run db:migrate`
- `npm run db:seed`

## Notes

- The migration script first tries direct Postgres access and falls back to the Supabase Management SQL API when direct DB networking is unavailable.
- This public repo is a showcase mirror, so deployment automation and secret-bearing configuration are intentionally excluded.
- Seeded accounts use the password defined in `shared/seed-data.ts`.
