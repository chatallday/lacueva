## Project verification facts

### Exact commands (from package.json)
- Tests: **unknown** — no test script defined in package.json
- Single-file test: **unknown** — no test script defined
- Typecheck: `npm run lint` (runs `tsc --noEmit`) — from package.json scripts.lint
- Lint: `npm run lint` (runs `tsc --noEmit`) — from package.json scripts.lint
- Build: `npm run build` (runs `vite build`) — from package.json scripts.build
- Integration/e2e: **unknown** — no test script defined
- Dev server: `npm run dev` (runs `tsx server.ts`) — from package.json scripts.dev
- Preview: `npm run preview` (runs `vite preview`) — from package.json scripts.preview
- Clean: `npm run clean` (runs `rm -rf dist`) — from package.json scripts.clean
- Image conversion: `npm run convert-images` (runs `tsx scripts/convert-to-webp.ts`) — from package.json scripts.convert-images

### Generated code or types
- TypeScript config: `noEmit: true` (tsconfig.json) — no .d.ts files emitted
- No code generation scripts found in package.json (convert-images is a utility, not type generation)
- Vite bundling only; no separate type generation command
- Vite multi-page build: index.html, admin.html, staff.html (vite.config.ts rollupOptions.input)

### Key connections between files
- Shared types: `tsconfig.json` paths alias `@/*` → `./*` (root); no centralized types file
- API client ↔ server handlers: Frontend calls `/api/*` endpoints; backend Express app in `server.ts` defines all routes; Vercel routes `/api/*` to `api/index.ts` which imports `app` from `server.ts`
- Database: Teable Cloud API via `teable.ts` (server) and `teable-client.ts` (frontend read-only); table IDs in `.env` / `.env.example`
- Config/env templates: `.env.example` — all env vars documented; `vite.config.ts` reads `DISABLE_HMR` and `GEMINI_API_KEY`
- Fixtures/mocks: **unknown** — none detected
- Frontend Teable client: `teable-client.ts` — read-only frontend wrapper; writes go through `/api/*`
- Server Teable client: `teable.ts` — full CRUD client used by `server.ts` and `api/*` functions

### Docs that act as instructions
- `INSTRUCTIONS.md` — project instructions (branding, hours, contact, Teable config, no-C-drive rule)
- `README.md` — project overview (Amate 38 legacy, env vars, features)
- `wiki/operational_rules.md` — operational rules (Teable tenant, branding, hours, menu, reservations, blackout, admin, Teable table IDs)
- `ENTITYOS_PROTOCOL.md` — entity OS protocol (45 bytes)
- `project_manifest.json` — project manifest (appName, restaurantId, baseTheme, devPort)
- `project_manifest.md` — project manifest markdown
- `metadata.json` — project metadata
- `.github/workflows/keepalive.yml` — Supabase keepalive cron (legacy, references old Supabase)
- `.vercelignore` / `.vercelignore.txt` — Vercel ignore rules
- `vercel.json` — Vercel deployment config (rewrites, crons, headers)