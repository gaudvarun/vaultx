# Vault — Lecture Repository

A course/lecture archive app powered by React + Vite + Supabase.

## Setup

```bash
npm install
npm run dev
```

## Environment Variables

Create a `.env.local` file:

```env
VITE_SUPABASE_URL=https:
VITE_SUPABASE_ANON_KEY=
VITE_ADMIN_PASSWORD=
```

## Deploy (Vercel / Netlify)

1. Push to GitHub
2. Import repo in Vercel or Netlify
3. Add the three env vars above in the dashboard
4. Build command: `npm run build`
5. Output dir: `dist`

## Supabase Schema

```sql
create table public.courses (
  id uuid primary key default gen_random_uuid(),
  name text not null,
  drive_link text not null,
  drive_folder_id text not null,
  description text,
  created_at timestamptz default now()
);
```

RLS is enabled with public read + public insert/delete policies (admin auth is handled in-app).
