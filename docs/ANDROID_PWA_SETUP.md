# Android installation and APK plan

## Phase 1 — Installable mobile web app
1. Host the app at a stable HTTPS URL.
2. Confirm manifest, icon, scope, start URL, and service worker are reachable without authentication.
3. Test Chrome Android install flow and standalone launch.
4. Test offline behavior; only the app shell is cached in this prototype.
5. Confirm accessibility, viewport, keyboard behavior, and slow-network experience.

## Phase 2 — Real-user release gate
Do not onboard the team until all of the following are true:
- Authentication, invitations, password reset, session expiration, and account revocation work.
- Every table has reviewed RLS policies and negative tests for cross-business data access.
- No secret keys are in client bundles or repository history.
- CRM, tasks, projects, finance, and dashboards read/write real database records with validation.
- Audit logging, backups, restore test, monitoring, privacy notice, and data-retention policy are ready.
- Seed/demo data is removed or clearly isolated from production.

## Phase 3 — Android APK
Choose one path after the production domain is stable:
- **Trusted Web Activity / PWABuilder:** suitable for a strong web-first PWA; Android signing and domain association may be required.
- **Capacitor:** suitable if native plugins, camera/files, push notifications, or more native app controls are needed.

Release tasks: set application ID, display name, icon/splash assets, version code/name, signing key, target SDK, permissions, deep links, privacy disclosures, and crash reporting. Test sign-in persistence, links, file uploads (if added), offline messaging, and logout on multiple Android versions.
