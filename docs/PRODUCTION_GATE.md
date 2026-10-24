# Production release gate

**Do not treat the current demo as production-ready.**

- [ ] Confirm legal/data boundary for GoldBuilders and each ecosystem business.
- [ ] Create managed hosting and database projects under organization-controlled accounts.
- [ ] Configure secrets in hosting environment settings, never in source control.
- [ ] Implement authentication, invitation flow, account recovery, and role administration.
- [ ] Review schema and enforce organization/business-unit scoping with PostgreSQL RLS.
- [ ] Test read/write access using at least owner, manager, staff, and cross-business accounts.
- [ ] Implement server-side input validation and authorization for every mutation.
- [ ] Replace all illustrative metrics with database queries and empty states.
- [ ] Implement CRM, tasks, projects, finance, people, goals, reports, and export workflows.
- [ ] Add audit trail for sensitive changes; restrict audit-log access.
- [ ] Configure rate limiting, abuse protection, error monitoring, and alerting.
- [ ] Enable automated backups and test restoration to a separate environment.
- [ ] Publish privacy notice, data retention/deletion process, and incident response contacts.
- [ ] Test mobile accessibility, secure cookies/session behavior, CSRF/XSS protections, and dependencies.
- [ ] Run staging acceptance tests; obtain business-owner approval.
- [ ] Deploy to production HTTPS domain and test rollback.
- [ ] Only then invite users and import real records.
