# LastSaaS

[![CI](https://github.com/jonradoff/lastsaas/actions/workflows/ci.yml/badge.svg)](https://github.com/jonradoff/lastsaas/actions/workflows/ci.yml)
[![codecov](https://codecov.io/gh/jonradoff/lastsaas/branch/master/graph/badge.svg)](https://codecov.io/gh/jonradoff/lastsaas)
[![Go Report Card](https://goreportcard.com/badge/github.com/jonradoff/lastsaas)](https://goreportcard.com/report/github.com/jonradoff/lastsaas)

**The last SaaS boilerplate you'll ever need.**

LastSaaS is a complete, production-ready SaaS foundation built entirely through conversation with [Claude Code](https://claude.ai/claude-code). It gives you multi-tenant account management, authentication, role-based access control, white-label branding, Stripe billing, API keys, outgoing webhooks, a full admin interface, system health monitoring, credit-based usage tracking, and product analytics with telemetry — everything you need to launch a SaaS business, ready to customize for your specific product.

The bottleneck for building software isn't engineering capacity anymore — it's imagination. LastSaaS proves it: a single person with a clear vision and an AI agent can stand up what used to require a team and months of work. And because it was built with [Claude Code](https://claude.ai/claude-code), the codebase is fork-ready for agentic engineering — point an AI agent at it and keep building your product through conversation.

**[Project Page](https://metavert.io/lastsaas)**

---

## Why LastSaaS Exists

Every SaaS product needs the same boring foundation: user accounts, teams, roles, authentication, admin dashboards, billing, usage limits, branding, webhooks, API keys. Historically, building that foundation meant weeks of plumbing before you could write a single line of your actual product.

LastSaaS eliminates that. Fork it, point an AI agent at it, and start building your product on top of a foundation that already handles:

- Multi-tenant isolation with role-based access
- JWT authentication with refresh token rotation
- Google, GitHub, and Microsoft OAuth integration
- Magic link passwordless authentication
- MFA/TOTP with recovery codes
- Email verification and password resets
- Team invitations and member management
- Stripe billing with subscriptions, per-seat pricing, trials, and credit bundles
- Plan entitlements and billing enforcement middleware
- White-label branding with custom themes, logos, landing pages, and custom pages
- API key authentication (admin and user scopes)
- Outgoing webhooks with 19 event types and HMAC-SHA256 signing
- Credit-based usage tracking (subscription + purchased buckets)
- Promotion codes and coupon management via Stripe
- Product analytics dashboard (conversion funnel, KPIs, retention cohorts, engagement metrics)
- Telemetry event system with Go SDK and REST API for custom event tracking
- A full admin interface for managing everything
- Built-in API documentation (HTML and Markdown)
- Real-time system health monitoring
- Financial metrics dashboard (revenue, ARR, DAU, MAU)
- MCP (Model Context Protocol) server for AI-powered admin access
- CLI tools for server administration
- Auto-versioning with database migrations
- Production deployment on Fly.io

This is open-source infrastructure for the agentic era of software — where the person with the idea is also the person who ships it. The codebase follows consistent patterns that AI agents navigate fluently, so you can keep evolving it the same way it was built.

---

## How It Compares

If you're evaluating SaaS boilerplates, you've probably looked at ShipFast, Supastarter, MakerKit, SaaS Pegasus, and Gravity. Here's why technical founders choose LastSaaS instead.

**Free and open-source.** ShipFast costs $169, MakerKit runs $199–599, Supastarter starts at $299, SaaS Pegasus charges $249/year, and Gravity is under $1K. LastSaaS is MIT-licensed — fork it, ship it, never pay a license fee. You own the code completely.

**Go backend, not another Next.js project.** ShipFast, Supastarter, MakerKit, and Gravity are all JavaScript/TypeScript stacks. SaaS Pegasus uses Django. LastSaaS pairs a Go backend with a React + TypeScript frontend — giving you compiled-binary deployment, low memory footprint (a 14MB Alpine container), and the concurrency model that Go is known for. If your SaaS will handle real traffic or you want a backend that isn't a Node.js monolith, this matters.

**Genuine multi-tenancy.** ShipFast has no multi-tenancy at all. SaaS Pegasus and Gravity offer basic team features but not true tenant isolation. LastSaaS gives you full multi-tenant architecture: tenant-scoped data isolation, three-tier RBAC (owner/admin/user), team invitations, ownership transfer, per-tenant activity logs, and per-tenant billing. This is the difference between "users can collaborate" and "each customer gets their own isolated workspace."

**White-label branding built in.** Most boilerplates give you a theme toggle at best. LastSaaS includes a full white-label system: custom app name, logo, colors, fonts, landing page, custom pages, CSS injection, favicon, configurable navigation with entitlement gating, and auth page customization. If you're building a platform where customers see your brand (not yours-plus-a-framework), this saves weeks.

**Outgoing webhooks, not just Stripe webhooks.** None of the alternatives — ShipFast, Supastarter, MakerKit, SaaS Pegasus, or Gravity — include an outgoing webhook system. LastSaaS ships with 19 event types across billing, team lifecycle, user lifecycle, credits, and security events, with HMAC-SHA256 signing, delivery tracking, and test events. Your customers can integrate with your platform from day one.

**API keys with scoped access.** ShipFast, Supastarter, and MakerKit don't include API key management. LastSaaS provides `lsk_`-prefixed API keys with admin and user authority scopes, SHA-256 hashed storage, and last-used tracking — ready for your customers to build integrations.

**Health monitoring and financial dashboards.** No competing boilerplate includes system health monitoring. LastSaaS collects CPU, memory, disk, HTTP, and MongoDB metrics every 60 seconds across all nodes, with 8 real-time charts, threshold alerting, and 30-day retention. The financial dashboard gives you revenue, ARR, DAU, and MAU time-series out of the box.

**Product analytics with telemetry.** No competing boilerplate includes product analytics. LastSaaS auto-instruments the customer journey — visitor → signup → plan page → checkout → paid conversion → upgrade — and visualizes it as a conversion funnel. The PM dashboard includes SaaS KPIs (MRR, ARR, ARPU, LTV, churn rate, trial conversion), retention cohort analysis, engagement metrics (DAU/WAU/MAU for paying subscribers), and a custom event explorer. A Go SDK and REST API let you track your own events with zero configuration.

**MCP server for AI-native operations.** This is unique to LastSaaS. A built-in Model Context Protocol server with 32 read-only tools lets you connect Claude (or any MCP-compatible AI) directly to your running application. Query your ARR trend, investigate error spikes, audit API keys, or review system health — all in natural language. No other SaaS boilerplate offers agentic admin access.

**Built for AI-assisted development.** LastSaaS was built entirely through conversation with Claude Code, and the codebase is designed to keep being built that way. Consistent patterns, clear naming, and a structure AI agents navigate fluently. Fork it, point an agent at it, describe your product, and keep going. The competing boilerplates were built for manual development — LastSaaS is built for the way software is made now.

| | LastSaaS | ShipFast | Supastarter | MakerKit | Pegasus | Gravity |
|---|---|---|---|---|---|---|
| **Price** | **Free (MIT)** | $169 | $299+ | $199–599 | $249/yr | <$1K |
| **Stack** | Go + React | Next.js | Next.js / Nuxt | Next.js | Django | Node + React |
| **Multi-Tenancy** | Full RBAC | — | ✓ | ✓ | Teams only | Teams only |
| **White-Label** | Full | — | Partial | Partial | — | — |
| **Webhooks** | 19 events | — | — | — | — | — |
| **API Keys** | Scoped | — | — | — | Basic | — |
| **Health Monitoring** | 8 charts | — | — | — | — | — |
| **Product Analytics** | 5-tab PM dashboard | — | — | — | — | — |
| **Credit System** | Dual buckets | — | — | Basic | — | — |
| **MCP Server** | 26 tools | — | — | — | — | — |
| **Admin Dashboard** | Full | — | ✓ | ✓ | ✓ | Basic |
| **Stripe Billing** | Full | ✓ | ✓ | ✓ | ✓ | ✓ |

---

## Features

### Authentication & Identity
- Email/password registration with bcrypt hashing
- Email verification via [Resend](https://resend.com)
- Google, GitHub, and Microsoft OAuth with automatic account linking
- Magic link passwordless login via email
- MFA/TOTP two-factor authentication with setup wizard
- Recovery codes for MFA backup access
- JWT access tokens (30min) + refresh tokens (7 days) with rotation
- Account lockout after failed login attempts
- Password reset flow with secure tokens
- Password strength enforcement
- Session management — list active sessions, revoke individual or all sessions
- Session revocation on password change

### Multi-Tenancy
- Root tenant (system admin) + customer tenants
- Users belong to tenants via memberships
- Roles: **owner**, **admin**, **user** with hierarchical permissions
- Team invitations with email notifications
- Ownership transfer between members
- Per-tenant activity log
- Tenant settings self-service

### Billing & Credits (Stripe)
- **Subscription plans** with monthly and annual billing (configurable annual discount %)
- **Pricing models**: flat-rate or per-seat (with included seats, min/max seat limits)
- **Free trials** with configurable trial days per plan and trial abuse prevention
- **Credit bundles** for one-time purchases
- **Dual credit buckets**: subscription credits (reset or accrue) + purchased credits
- **Stripe Checkout** (redirect-based) for payment collection
- **Stripe Billing Portal** for customer self-service (payment methods, invoices)
- **Multi-currency support** with configurable default currency
- **Stripe Tax** automatic tax calculation
- **Promotion codes and coupons** — create and manage via admin UI, linked to Stripe
- **Invoice generation** — sequential invoice numbers, PDF download, tax breakdown
- **Transaction history** — per-tenant and admin-wide with search and filtering
- **Financial metrics** — revenue, ARR, DAU, MAU time-series with charting
- **Billing enforcement middleware** — blocks expired subscriptions from paid features
- **Entitlement middleware** — gate features based on plan (boolean and numeric entitlements)
- **Billing waiver** for special accounts (root tenant, demo accounts)
- **Admin subscription management** — cancel, modify, reassign plans
- **Refund and dispute handling** — webhook handlers for `charge.refunded`, `charge.dispute.created`, `charge.dispute.closed`

### White-Label Branding
- Custom app name, tagline, and logo (text, image, or both modes)
- Theme colors (primary, accent, background, surface, text) with auto-generated shade palettes
- Custom fonts (body and heading)
- Custom landing page with configurable HTML
- Custom pages served at `/p/{slug}` with SEO metadata
- Custom CSS injection
- Custom head HTML injection (analytics, meta tags)
- Favicon upload
- Media library for image/asset management
- Configurable navigation sidebar with entitlement-gated items
- Auth page customization (login/signup headings and subtext)
- Dashboard HTML customization
- Open Graph image support

### API Keys
- Create API keys with `lsk_` prefix
- Two authority levels: **admin** (auto-resolves root tenant) and **user** (requires X-Tenant-ID)
- SHA-256 hashed storage — raw key shown only at creation
- Last-used timestamp tracking
- Admin UI for key management
- Supports both JWT and API key authentication on all endpoints

### Outgoing Webhooks
- 19 event types across 5 tiers:
  - **Billing**: subscription.activated, subscription.canceled, payment.received, payment.failed
  - **Team lifecycle**: member.invited, member.joined, member.removed, member.role_changed, ownership.transferred
  - **User lifecycle**: user.registered, user.verified, user.deactivated
  - **Credits & billing**: credits.purchased, plan.changed, tenant.created, tenant.deactivated
  - **Audit & security**: user.deleted, tenant.deleted, api_key.created, api_key.revoked
- HMAC-SHA256 payload signing with `whsec_`-prefixed secrets
- Delivery tracking with response codes, response bodies, and duration
- Test event delivery
- Secret regeneration
- Event type filtering per webhook

### Admin Interface
- **Dashboard** with user/tenant counts, health overview, and business metrics
- **User management** — list, search, view profiles, edit, suspend, impersonate, delete with ownership preflight
- **Tenant management** — list, view, edit, plan assignment, status control, subscription management
- **Financial overview** — transaction history across all tenants, revenue/ARR/DAU/MAU charts
- **Product analytics** — conversion funnel, SaaS KPIs, retention cohorts, engagement metrics, custom event explorer
- **Plan management** — create, edit, archive, entitlements, per-seat configuration, trial days
- **Credit bundle management** — create, edit, sort, activate/deactivate
- **Promotions** — create and manage Stripe promotion codes and coupons
- **Branding editor** — theme colors, logos, fonts, landing page, custom pages, CSS, navigation
- **API key management** — create, view, revoke
- **Webhook management** — create, edit, delete, test, view delivery history
- **Announcements** — publish system-wide announcements
- **System log viewer** with severity filtering, search, and user filtering
- **Configuration variable editor** (strings, numbers, enums, templates)
- **In-app messaging** — send messages to individual users
- **Root members** — manage the admin team with invitations and role changes
- **CSV export** for users and tenants
- **Admin impersonation** — log in as any user for debugging
- **System health monitoring** (see below)
- **Integration health checks** — MongoDB, Stripe, Resend, Google OAuth status
- Three-tier admin access: **user** (read-only), **admin** (read-write), **owner** (destructive operations)

### System Health Monitoring
- Automatic node registration with heartbeat (30s interval)
- Metrics collection every 60s: CPU, memory, disk, network, HTTP request stats, MongoDB stats, Go runtime
- HTTP metrics middleware with percentile latency tracking (p50/p95/p99)
- Threshold-based alerting (configurable warning/critical levels)
- 30-day automatic data retention via MongoDB TTL indexes
- Real-time dashboard with 8 time-series charts (Recharts)
- Aggregate, all-nodes overlay, and single-node filter modes
- Time range selection: 1h, 6h, 24h, 7d, 30d
- Integration health panel (MongoDB, Stripe, Resend, Google OAuth connectivity)

### Product Analytics & Telemetry
- **Conversion funnel** — Visitors → Signups → Plan Page Views → Checkouts → Paid Conversions → Upgrades, with conversion rates at each step
- **SaaS KPIs** — MRR, ARR, ARPU, LTV, churn rate, trial-to-paid conversion rate, median time to first purchase, active subscriber count
- **Retention cohorts** — weekly or monthly cohort retention table with color-coded heatmap (tracks `lastLoginAt` over time)
- **Engagement metrics** — DAU/WAU/MAU for paying subscribers, average sessions per user, top features by usage, credit consumption trend
- **Custom event explorer** — browse all event types, view trend charts, filter by name and time range
- **Telemetry Go SDK** — `telemetry.Track()` / `TrackBatch()` / `TrackPageView()` / `TrackCheckoutStarted()` / `TrackLogin()` for direct in-process event recording (no HTTP overhead)
- **Telemetry REST API** — `POST /telemetry/track` (anonymous, rate-limited) for page views; `POST /telemetry/events` and `/telemetry/events/batch` (authenticated) for custom events
- **Auto-instrumentation** — registration, email verification, login, checkout, subscription activation/cancellation, and plan changes are tracked automatically
- **365-day retention** — telemetry events auto-expire via MongoDB TTL index
- **Rate limiting** — 60 req/min per IP for anonymous tracking, 120 req/min per user for authenticated events

### User Self-Service
- Profile editing (display name, email)
- Theme preference (light/dark)
- Password management
- MFA setup and management
- Session viewer with remote revocation
- Account deletion with data cleanup
- Data export (GDPR-friendly)
- Billing management (plan selection, credit purchases, invoice history, PDF download)
- Onboarding flow

### Built-in API Documentation
- Interactive HTML API reference at `/api/docs` with expandable endpoint details
- Markdown API reference at `/api/docs/markdown` for integration in external docs
- Comprehensive webhook event reference with payload descriptions
- Auto-versioned from the VERSION file

### CLI Administration
- `lastsaas setup` — Initialize the system (create root tenant + owner)
- `lastsaas start` / `stop` / `restart` — Server process management
- `lastsaas change-password` — Reset any user's password
- `lastsaas send-message` — Send system messages to users
- `lastsaas transfer-root-owner` — Transfer root tenant ownership
- `lastsaas config list|get|set` — Manage configuration variables
- `lastsaas version` — Show binary and database versions
- `lastsaas status` — Check system health
- `lastsaas mcp` — Start the MCP server (see [MCP Server](#mcp-server-ai-admin-access) below)

### MCP Server (AI Admin Access)

A built-in [Model Context Protocol](https://modelcontextprotocol.io) server gives AI assistants like Claude read-only access to your admin data — dashboards, users, tenants, financials, logs, health, and more. Useful for asking questions like "what's our ARR trend?" or "show me critical logs from the last hour" in natural language.

- **32 read-only tools** across 14 categories — no write operations, safe by design
- **2 resources** — `lastsaas://dashboard` and `lastsaas://health` for automatic context
- **API key authentication** — requires a root-tenant API key, same auth as the admin API
- **Stdio transport** — runs locally, compatible with Claude Desktop and Claude Code

**Tool categories:**
- **About** — software version and environment
- **Dashboard** — user/tenant counts, health overview
- **Tenants** — list with filtering, detailed view with members
- **Users** — list with search, detailed view with auth methods and memberships
- **Financial** — transaction history, revenue/ARR/DAU/MAU time-series metrics
- **Logs** — full-text search with severity/category/date filters, severity counts
- **Health** — current system metrics, time-series health data, node list, integration status
- **Config** — list and inspect runtime configuration variables
- **Plans** — plan details, entitlement keys, credit bundles
- **Announcements** — list published and draft announcements
- **Promotions** — Stripe promotion codes with coupon details
- **Security** — API key inventory (previews only), root tenant members
- **Webhooks** — webhook configs, event type reference, delivery history

### Security
- Security headers (CSP, HSTS, X-Frame-Options, X-Content-Type-Options, Referrer-Policy, Permissions-Policy)
- Rate limiting on authentication endpoints
- Request body size limits
- NoSQL injection protection (regex input escaping)
- XSS protection via DOMPurify for injected HTML
- Trusted proxy IP resolution (Fly-Client-IP)
- Webhook signature verification (Stripe inbound, HMAC-SHA256 outbound)
- Idempotent webhook processing via unique event ID index
- System log injection detection with automatic critical alerts
- Refresh token rotation with family-based revocation

### Production Ready
- Dockerized multi-stage build (Go + Node + Alpine)
- Fly.io deployment with auto-stop/auto-start machines
- SPA serving from the Go binary (no s