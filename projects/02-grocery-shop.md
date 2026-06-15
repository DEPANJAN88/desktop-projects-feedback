# Project 2: Smart Grocery Shop Management System v2.0

**Path:** `C:\Users\depan\desktop\MyFirstProject\grocery_shop`  
**Type:** Commercial offline business software  
**Target user:** Grocery shop owners in remote India (cash + credit sales)

---

## What It Does

### Core Business
- Customer CRM with segments (Premium / Regular / Occasional)
- Product master with cost, selling price, margin %, stock tracking
- Cash + credit sales with multi-item line details
- Payment recording and automatic outstanding balance reduction
- Locked transactions (anti-fraud — no edit/delete after save)

### Business Intelligence
- Top 10 profitable products
- Loss-making / low-margin product alerts
- Slow-moving inventory detection
- Monthly sales & profit reports
- Customer-wise profitability analysis
- Smart suggestions (promotions, collections, bundling)

### Production / Commercial (v2.0)
- Owner + Staff login with role-based access
- One-time setup wizard
- 30-day trial + offline license key activation
- CSRF protection + login brute-force lockout
- Waitress production server (Windows-friendly)
- Auto-backup on startup
- Audit log with user ID and IP
- Fully offline CSS (no CDN)
- Excel, PDF, CSV export
- LAN mode for shop tablets

## Tech Stack

| Layer | Technology |
|-------|------------|
| Backend | Python 3.9+ / Flask 3 |
| Database | SQLite (single-file, easy backup) |
| Frontend | HTML + custom offline CSS |
| Production server | Waitress |
| Security | Flask-Login, Flask-WTF, PBKDF2 passwords |

## Strengths ✅

- **Commercially viable** — install.bat + run_production.bat = one-click for non-technical users
- **Offline-first** — works without internet after install (critical for rural India)
- **Data integrity** — immutable sales/payments, full audit trail
- **Indian format** — ₹ currency, DD/MM/YYYY dates
- **Large readable UI** — tablet/laptop friendly for shop owners
- **License system** — vendor can generate keys via `tools/generate_license.py`
- **Well documented** — README.md + DEPLOYMENT.md

## Gaps / Risks ⚠️

- **Single-machine only** — SQLite doesn't support multi-PC simultaneous access (LAN read OK, not multi-write)
- **Default test credentials exist** — change `owner`/`secret123` immediately
- **LICENSE_SECRET is default** — must change before commercial distribution
- **No mobile app** — browser-only (responsive but not native)
- **No SMS/WhatsApp reminders** for outstanding credit (future feature)
- **venv/ and data/ not in git** — need `.gitignore` before pushing source

## How to Run

```bat
cd C:\Users\depan\desktop\MyFirstProject\grocery_shop
install.bat          # first time only
run_production.bat   # daily use
```

Open: http://127.0.0.1:5000

## Feedback Score: 9/10

**Verdict:** This is your strongest, most deployable product. Ready for pilot deployment with 1–2 real shops. Change secrets, package as ZIP, and start selling.

## Commercial Deployment Checklist

- [ ] Change `LICENSE_SECRET` in `.env`
- [ ] Change owner password in Settings
- [ ] Test backup & restore procedure
- [ ] Create customer ZIP (exclude venv, include install.bat)
- [ ] Generate license keys per customer
- [ ] Pilot with 1 shop for 2 weeks
- [ ] Collect feedback on UI text size and Hindi language need

## Suggested Next Steps

1. Push clean source to GitHub: `smart-grocery-shop` (with .gitignore)
2. Add Hindi UI option (big market in rural India)
3. Add WhatsApp-style payment reminder export
4. Build Windows installer (.exe) using Inno Setup for non-technical customers
