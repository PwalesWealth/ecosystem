# GoldBuilders OS — Android-ready PWA starter

This project is now configured as an installable Progressive Web App (PWA) shell. It is designed to be opened on Android through a secure HTTPS website and added to the home screen. A native Android APK can be produced after the hosted app and its production backend are configured.

## Current state — read before use

**Status: installable prototype shell; not yet a live business system.**

Included now:
- Responsive dashboard and ecosystem directory
- PWA manifest, app icon, install prompt, and service-worker shell cache
- Offline opening of the cached demo shell
- Deployment and production-readiness checklists

Not included / not yet completed:
- Real user authentication or invitations
- Live database-backed CRM, tasks, projects, finance, reporting, or audit history
- Production security validation, monitoring, backup/recovery tests, or deployed URL
- Signed APK

The dashboard contains illustrative metrics and demo records. Do not enter confidential or real customer/employee/financial information. Offline mode caches the demo interface only; it does not sync business records.

## Preview locally

For a quick UI preview, open `index.html`. PWA install and service-worker functionality require a secure context: deploy over HTTPS or use a local development server. Opening the file directly (`file://`) will not enable PWA installation.

## Deploy the demo PWA shell

1. Create a Git repository and push this project.
2. Deploy the static project to a hosting provider that supports HTTPS (for example, Vercel, Netlify, or Cloudflare Pages).
3. Ensure `index.html`, `manifest.webmanifest`, `sw.js`, and `icons/icon.svg` are served from the same path and that the manifest has the correct scope if using a subpath.
4. Open the HTTPS URL in Chrome on Android. Use the in-app Install app prompt when shown, or Chrome menu → **Install app** / **Add to Home screen**.

This makes the demo shell installable; it does not make the demo records live or secure for real business use.

## Production architecture to complete next

- App: Next.js + TypeScript, or another maintained application framework
- Identity and database: Supabase Auth + PostgreSQL with Row Level Security (RLS)
- Hosting: managed HTTPS hosting
- Data access: server-side validation, least-privilege roles, business-unit authorization, audit trail
- Operational controls: backups and restore test, monitoring, error reporting, privacy notice, retention policy, incident response

Before importing real data, review and test every RLS policy using owner, manager, staff, and cross-business test accounts. Never expose a Supabase service-role key in browser code. Store only the public/anon key in client configuration, and rely on verified RLS plus server-side authorization.

## APK path after deployment

Once the PWA is live at its final HTTPS domain and passes security/accessibility checks, use a PWA-to-Android packaging route such as PWABuilder / Trusted Web Activity, or wrap the production web app with Capacitor. Configure app ID, signing key, icons, versioning, offline behavior, and deep links. Test on real Android devices before distributing an APK. Keep signing keys private and backed up securely.
