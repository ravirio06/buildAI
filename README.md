# BuildAI — free AI website builder MVP

A working, local-first React/Vite MVP inspired by AI website builders. It has no plans, subscriptions, credits, token counter, artificial generation limits, or locked features.

## Run

```bash
npm install
npm run dev
```

## What works now

- Natural-language prompt to deterministic local website generation
- Three-panel builder: files/pages, AI chat, live preview
- Conversation edits for colors, hero sizing, testimonials, forms, login, admin dashboard, responsiveness, fonts, animation flag and dark mode
- Desktop/tablet/mobile preview controls
- Unlimited projects in browser localStorage
- Rename/open/delete projects
- Free templates for SaaS, Portfolio, Business, Restaurant, E-commerce, Blog, Agency, Landing page, Dashboard and Personal website
- Progress UI for generation steps
- Publish state and in-app preview URL pattern
- Export a standalone HTML file
- Optional Supabase environment configuration for real authentication/storage

## Real AI provider connection

The MVP intentionally does not pretend to call an AI API when no provider is configured. Add a server-side `/api/ai` route (Vercel/Netlify/Cloudflare/Supabase Edge Function) and keep `AI_API_KEY` server-side. The browser must never receive provider secrets.

A production implementation can replace `generateSite()` / `applyEdit()` with structured model output while keeping the same UI and state model.

## Authentication

Without Supabase variables, the sign-in UI creates a local demo session. For production authentication, set `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY` and wire the provided UI to Supabase Auth. Do not store passwords in this app.

## Free publishing

The preview is served by the same application and can be exposed at a route such as `/preview/:projectId` when routing is added. The current MVP's Publish action records publish state and provides export. Public hosting requires a host account/domain and is therefore intentionally left as a hosting adapter rather than faked.
