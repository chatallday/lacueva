# La Cueva Del Chango PWA

## Environment Variables
- `GEMINI_API_KEY`: Required for the AI Concierge chat.
- `TEABLE_TOKEN`: Server-only Teable PAT
- `ADMIN_PASSWORD`: Admin portal password

## Critical Working Directory Rule
- **NEVER access the C: drive.** All work must be done within the project folder: `F:\Mike d drive\Mike Webs\Client Projects\Amate and Changa\La Cueva del Chango\cueva-pwa`
- The default working directory `C:\Users\470 G3\Documents\Default Project` is NOT the project folder.
- Never read, write, or execute commands targeting C: drive paths.
- Always use the project folder path for all file operations.

## Features
- Luxury Jungle Theme (Forest Green & Sandy Gold)
- Multi-language Support (English/Spanish)
- AI Concierge with "Playa-casual" tone
- Menu with GSAP "unfolding leaf" animations
- Multi-channel Chat (WhatsApp, SMS, Voice, Messenger)
- Resident vs Visitor booking flow
- Teable database (no Supabase)
- Vercel deployment (CLI-based, no GitHub auto-deploy)