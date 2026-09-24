# Project SUPER 50 — one website

Same URL for everyone. Viewers see live data without login. The administrator logs in on the same page and gets the Excel/CSV upload controls.

## Setup
1. Create Supabase project.
2. Run `supabase-schema.sql`.
3. Create the administrator in Supabase Authentication → Users.
4. Insert that exact email into `admin_users` (SQL comment in schema).
5. Copy `supabase-config.example.js` to `supabase-config.js` and add Project URL + anon/publishable key.
6. Push to GitHub and deploy as a static site (Vercel/Netlify/etc.).

The existing four data upload types are stored in Supabase in 300-row chunks. Realtime metadata changes cause every open dashboard to reload the affected dataset. RLS prevents viewers from writing. Never use a service-role key in the browser.

