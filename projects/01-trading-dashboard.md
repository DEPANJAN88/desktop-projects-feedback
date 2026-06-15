# Project 1: Personal Trading Dashboard

**Path:** `C:\Users\depan\desktop\MyFirstProject`  
**Type:** Personal website + live market tracker  
**Built for:** Depanjan Nath (Indian equity & derivatives trader)

---

## What It Does

- Personal trader branding site with clean blue professional design
- **Live indices dashboard** with Chart.js charts (simulated data)
- **Advanced option chain** with Greeks (Delta, IV)
- **PCR trend** analysis display
- **Paper trade simulator**
- **Live news feed** section
- **Zerodha integration** buttons with dual-backend auto-detection

## Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | HTML + Tailwind CSS + Chart.js + Font Awesome |
| Backend A | Node.js + Express + kiteconnect (port 3000) |
| Backend B | Python FastAPI + kiteconnect (port 8000) |

## Strengths ✅

- **Visually polished** — professional trader aesthetic, responsive layout
- **Feature-rich frontend** — option chain, Greeks, paper trading in one page
- **Flexible backend** — choose Node or Python depending on preference
- **Zero install for demo** — double-click `index.html` works immediately with simulated data
- **Auto-detects backend** — frontend tries port 3000 then 8000

## Gaps / Risks ⚠️

- **Simulated data by default** — not connected to live markets without Zerodha API setup
- **Backends are templates** — need real API keys from developers.zerodha.com
- **No authentication** — anyone opening the page sees everything
- **CDN dependent** — Tailwind, Chart.js, fonts load from internet (not offline)
- **Not production-hardened** — no HTTPS, rate limiting, or session management on backends
- **No git repo** — source not version-controlled yet

## How to Run

```bat
# Frontend only (simulated data)
start C:\Users\depan\desktop\MyFirstProject\index.html

# Node backend
 cd backend && npm install && node server.js

# Python backend
 cd backend-python && pip install -r requirements.txt && uvicorn main:app --reload
```

## Feedback Score: 7/10

**Verdict:** Excellent personal portfolio / paper-trading tool. Not yet a production trading platform. Next step is Zerodha API integration and optional user login.

## Suggested Next Steps

1. Add Zerodha API keys to `.env` in chosen backend
2. Test "Connect to Backend" button end-to-end
3. Add disclaimer banner: "Paper trading / educational only"
4. Push to GitHub repo: `trading-dashboard`
