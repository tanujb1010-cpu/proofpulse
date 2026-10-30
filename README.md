# ProofPulse ⚡ - High-Conversion Social Proof & Testimonial Micro-SaaS

> **Turn customer love into paying customers.** Collect, curate, and embed high-converting Walls of Love, live conversion toasts, avatar stacks, and rating badges with 1 line of JavaScript.

---

## 🚀 Why This Micro-SaaS Makes Real Recurring Revenue

Indie hackers, SaaS founders, agency owners, course creators, and e-commerce merchants are willing to pay **\$19–\$49/month** because **social proof directly increases conversion rates by 15%–30%**.

### Core Revenue Streams
1. **Starter Plan (\$0/mo)**: Up to 15 testimonials, 1 space, standard widget, "Powered by ProofPulse" watermark (acts as a viral customer acquisition loop).
2. **Pro Plan (\$19/mo)**: Unlimited testimonials, 5 spaces, All 5 widgets (Wall of Love, Toasts, Marquee, Carousel, Badge), AI Hook Extractor, Remove watermark, Social Card Studio (PNG/SVG export).
3. **Agency Plan (\$49/mo)**: Unlimited spaces, video testimonial collection, custom CNAME domains (`proof.clientdomain.com`), webhooks, team seats.

---

## 🛠️ Complete Feature Set

- **Public Collection Spaces (`/collect/:slug`)**: Responsive customer submission forms with 5-star ratings, custom guided prompt questions, avatar selection, and confetti animation.
- **AI Testimonial Enhancer**:
  - Automatically extracts 1-sentence punchy sales hooks from long reviews.
  - Computes sentiment confidence scores (Positive / Neutral / Critical).
  - Auto-classifies keyword tags (`#ROI`, `#Speed`, `#Productivity`, `#Customer Support`).
- **Interactive Widget Studio**: Live customizable split-screen editor for:
  - *Wall of Love* (Responsive Grid & Masonry with tag filters)
  - *Live Conversion Toasts* (Floating real-time notifications, e.g., "Alex from HyperStack just rated 5 stars")
  - *Infinite Marquee Strip* (Smooth continuous testimonial ticker)
  - *Interactive Carousel Slider* (Touch/arrow responsive testimonial slider)
  - *Avatar Stack & Rating Badge* (Compact hero badge: "⭐⭐⭐⭐⭐ 4.9/5 from 320+ customers")
- **1-Line Universal Embed Engine (`/embed.js`)**: Works on any website (Webflow, Framer, WordPress, Shopify, Next.js, HTML) without CSS conflicts.
- **Viral Social Card Studio**: Turn testimonials into high-res graphic cards for X/Twitter and LinkedIn with customizable gradient themes.
- **Conversion & Telemetry Analytics**: Tracks widget impressions, clicks, sentiment distribution, and form conversion funnels.
- **Multi-Product Spaces**: Manage different SaaS apps, e-com stores, or agency clients under one account.

---

## 📁 Project Architecture

```
proofpulse/
├── standalone-app.html        # Zero-dependency browser-runnable full application
├── server/                    # Node.js Express REST API & Embed CDN
│   ├── server.js              # REST API endpoints & static embed server
│   ├── db.js                  # Persistent JSON/SQLite database storage
│   ├── ai.js                  # AI Hook extractor & sentiment analyzer
│   ├── package.json
│   └── public/
│       ├── embed.js           # Universal 1-line client embed script
│       └── test-embed.html    # External website embed test sandbox
├── client/                    # React 18 + Vite + Tailwind CSS Frontend
│   ├── src/
│   │   ├── main.jsx           # React root
│   │   ├── App.jsx            # App router & modal layout
│   │   ├── context/AppContext.jsx
│   │   ├── components/        # Navbar, Sidebar, MetricCard, TestimonialCard, Modals
│   │   ├── components/widgets/ # WallOfLove, Toast, Marquee, Carousel, Badge
│   │   ├── pages/             # Landing, Dashboard, Inbox, Studio, Collect, Analytics, Settings
│   │   └── lib/api.js         # API bridge with offline fallback
│   ├── package.json
│   ├── vite.config.js
│   └── tailwind.config.js
└── package.json               # Root monorepo runner
```

---

## ⚡ How to Run

### Option 1: Instant Zero-Dependency Browser Preview (No installation required)
Simply double-click or open `standalone-app.html` in any browser (Chrome, Edge, Safari, Firefox):
```bash
# Double click in file explorer:
C:\Users\TANUJ\.gemini\antigravity\scratch\proofpulse\standalone-app.html
```

### Option 2: Full-Stack Node + React Development Server
```bash
# 1. Install dependencies
cd server && npm install
cd ../client && npm install

# 2. Start backend server (Port 4000)
cd ../server && npm run dev

# 3. Start frontend app (Port 3000)
cd ../client && npm run dev
```

Visit:
- **Frontend App**: `http://localhost:3000`
- **Embed Script**: `http://localhost:4000/embed.js`
- **Live Embed Sandbox**: `http://localhost:4000/test-embed.html`

---

## 🌐 Deploying to Production

1. **Frontend (Vercel / Netlify)**: Deploy `client/` pointing to your production backend.
2. **Backend (Render / Railway / Fly.io)**: Deploy `server/` with `NODE_ENV=production`.
3. **Stripe Integration**: Configure your Stripe secret keys in `server/server.js` to accept live payments.
