# MediCare — Local / No-Credentials Build

This version is modified to run as a normal Vite web app without Supabase, OpenAI, or any paid API credentials.

## Run

```bash
npm install
npm run dev
```

For production hosting:

```bash
npm run build
```

Deploy the generated `dist/` directory to any static host.

## What changed

- Removed the runtime dependency on Supabase URLs/keys.
- Removed OpenAI API calls from the chatbot.
- Added a browser-local data layer using `localStorage`.
- Hospital departments, doctors, FAQs, appointments, users, conversations, and knowledge-base documents work locally.
- The chatbot uses deterministic, keyword-based hospital guidance and does not require an AI API key.
- The original `supabase/` Edge Functions/migrations are no longer used by the frontend.

## Important

This is a **single-browser/demo deployment**. Data is stored in each visitor's browser and is not shared between users or devices. It is not suitable for real patient data or production medical records without a real authenticated backend and appropriate security/privacy controls.

No `.env` file is required. `.env.example` documents that intentionally.

## Local admin dashboard

The app includes a fully local admin account. No Supabase, OpenAI, or paid API credentials are required.

- Admin URL: `/admin`
- Email: `admin@medicare.local`
- Password: `admin123`
- Admin appointment status changes are persisted in browser `localStorage`.

Use **Use demo admin login** on the sign-in screen to fill the credentials automatically. This local admin is intended for demos/testing and is not suitable for production medical data.
