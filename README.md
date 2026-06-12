# Hi, I'm Josh Ade

Co-founder and lead developer of [**Built For Small Business**](https://builtforsmallbusiness.com), a free, production-grade business management platform serving UK SMEs.

I build full-stack web applications with Laravel. I care about shipping real things that solve real problems, writing clean, maintainable code, and understanding the business context behind every feature.

---

##  What I'm building — Built For Small Business

> A free all-in-one platform covering invoicing, expenses, payroll, client management, and financial reporting, built for small businesses in the UK.

**Live at → [builtforsmallbusiness.com](https://builtforsmallbusiness.com)**

### The problem it solves

Most accounting tools are either too expensive, too complex, or ignore non-Western markets entirely. BFSB is permanently free at its core, with UK and compliance built in, not bolted on.

### What I built

| Module | What it does |
|---|---|
| **Invoicing** | Create, send, and track invoices with Stripe payment integration and a 0.5% platform fee model |
| **Expenses** | Log, categorise, and bulk import expenses (CSV/XLSX) with magic byte validation and queued processing |
| **Payroll** | Full payslip generation with country-conditional columns (UK PAYE vs Nigerian tax logic) |
| **Financial Reporting** | Profit & Loss reports with PDF export, tax year scoping (GB: April–March, NG: calendar year) |
| **Subscriptions** | Stripe billing with cancel/refund flows, plan tier gating, and a Business plan gifting system |
| **PDF Generation** | Browsershot/Puppeteer for invoice and report PDFs, including base64 font embedding for reliable rendering |
| **Data Export** | Multi-sheet Excel exports via Maatwebsite, CSV/XLSX import pipelines with security hardening |
| **Blog & Content** | AI-powered content pipeline using the Anthropic API for voiceover scripts and audio generation |

### Architecture decisions worth knowing about

- **Multi-country tax logic** via `TaxYearService` with `scopeForTaxYear` scoped across invoices, expenses, and payslips — one codebase handles GB and NG compliance correctly
- **Subscription hardening** — corrected Stripe API version compatibility for refunds, implemented live Stripe status checks in cancellation logic, tracked payment intents separately from subscriptions
- **Import security** — CSV/XLSX expense imports validate mime type *and* magic bytes before queued processing, preventing spoofed file uploads
- **PDF reliability** — base64-encoded fonts loaded at render time, so Browsershot/Puppeteer produces consistent output across environments
- **Dashboard caching** — `Cache::remember` across expensive aggregates to keep the dashboard fast without a dedicated data layer
- **Paywall pattern** — feature discovery modal that gates on plan tier without blocking exploration, keeping the free tier genuinely useful

### Tech stack

```
Backend:    Laravel 12, PHP, MySQL
Frontend:   Blade, Bootstrap, Alpine.js, Chart.js
Payments:   Stripe (subscriptions, refunds, payment intents)
PDFs:       Browsershot + Puppeteer, base64 font loading
Exports:    Maatwebsite Excel (multi-sheet), custom CSV pipeline
Storage:    Cloudflare R2 (backups), Namecheap VPS
Queue:      Laravel jobs for import processing, email dispatch
APIs:       Anthropic (content pipeline), ElevenLabs (audio)
Tax/Compliance: UK (HMRC MTD registered), Nigeria (calendar year)
```

---

## 🛠 Skills

```
Languages:     PHP, JavaScript, HTML/CSS
Frameworks:    Laravel, Alpine.js, Bootstrap
Databases:     MySQL
Tools:         Git, Composer, npm, Puppeteer
Integrations:  Stripe, Cloudflare, Anthropic API
Other:         REST APIs, queued jobs, PDF generation, Excel/CSV pipelines
```

---

## Let's connect

- 🌐 [builtforsmallbusiness.com](https://builtforsmallbusiness.com)
- 🐦 [@manlikeroot](https://x.com/manlikeroot)
- 💼 Open to remote Laravel roles

---

*"If it doesn't challenge you, it won't change you."*
