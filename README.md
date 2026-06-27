# 🌳 Tree of Knowledge

**Philosophie als lebendiges Universum** — interaktive Wissensplattform mit 25+ Philosophen, 5 Ansichten, lokaler KI (Ollama) und automatischem Wikipedia-Scraper.

![Tree of Knowledge](docs/preview.png)

---

## ⚡ Schnellstart

### Option A — Standalone HTML (kein Setup)
```bash
# Einfach öffnen:
open index.html

# Oder hosten auf Netlify, GitHub Pages, Cloudflare Pages
```

### Option B — Vollständige App (Next.js + DB + KI)
```bash
bash setup.sh
# → http://localhost:3000
```

---

## Features

| | |
|---|---|
| 🌳 Baum mit echten Blättern + Wind | 🎮 Quiz (Zitate, Ideen, Epochen) |
| 🍎 25 Philosophen als leuchtende Äpfel | ★ Lernfortschritt + Checkmarks |
| 📸 Wikipedia-Portraits (live) | 🎲 Zufalls-Entdeckung |
| 🕸 Mind Map mit Einfluss-Pfeilen | 🔗 Teilbare Links (#philosopher=kant) |
| 📅 Chronologische Timeline | ⬇ Offline-Download |
| 🌌 Galaxie-Ansicht (D3 Force, draggbar) | 💡 Concept Explorer |
| 🔍 Echtzeit-Suche | ⌨ Keyboard-Shortcuts |
| 🦙 Ollama KI-Chat + Streaming | 📱 PWA installierbar |
| 🌍 DE / EN / عر (RTL) | 🗄️ PostgreSQL + Prisma |

---

## Projektstruktur

```
tree-of-knowledge/
│
├── index.html                  ← 🌟 Standalone-App (66 KB, kein Build nötig)
│
├── src/                        ← Next.js Produktions-App
│   ├── app/
│   │   ├── api/ai/             ← Ollama-Proxy (CORS-frei)
│   │   └── api/philosophers/   ← REST API (Prisma → PostgreSQL)
│   ├── components/
│   │   ├── Tree/               ← SVG-Baum mit Blättern
│   │   ├── Views/              ← MindMap, Timeline
│   │   ├── Sidebar/            ← Philosopher-Panel + KI-Chat
│   │   └── UI/                 ← Header, OllamaModal
│   ├── lib/
│   │   ├── db.ts               ← Prisma Client
│   │   └── ollama.ts           ← Streaming KI-Client
│   ├── stores/treeStore.ts     ← Zustand (globaler State)
│   └── types/index.ts          ← TypeScript-Typen
│
├── prisma/
│   ├── schema.prisma           ← Datenbankschema
│   └── seed.ts                 ← 25 Philosophen als Seed
│
├── scripts/
│   ├── scrape-wikidata.ts      ← Auto-Scraper (80+ Philosophen)
│   └── detect-influences.ts    ← Einfluss-Netzwerk-Erkennung
│
├── .github/workflows/
│   ├── deploy.yml              ← CI/CD → Vercel
│   └── pages.yml               ← GitHub Pages für index.html
│
├── docs/
│   ├── DEPLOYMENT.md           ← Vollständige Deploy-Anleitung
│   ├── HOSTING.md              ← Hosting-Guide (5 Plattformen)
│   └── nginx.conf              ← Nginx-Konfiguration
│
├── docker-compose.yml          ← PostgreSQL + Ollama + pgAdmin
├── Dockerfile                  ← Produktions-Image
├── setup.sh                    ← Ein-Befehl-Setup
├── vercel.json                 ← Vercel-Konfiguration
└── netlify.toml                ← Netlify-Konfiguration
```

---

## Deployment

### GitHub Pages (index.html)
Repo → Settings → Pages → Source: **GitHub Actions**  
→ Automatisch bei jedem Push auf `main`

### Vercel (Next.js App)
```bash
npm i -g vercel && vercel --prod
```
Alle Env-Variablen aus `.env.example` in Vercel setzen.

### Supabase (Datenbank)
1. [supabase.com](https://supabase.com) → Neues Projekt
2. Connection String als `DATABASE_URL` setzen
3. `npm run db:push && npm run db:seed`

→ Vollständige Anleitung: [docs/DEPLOYMENT.md](docs/DEPLOYMENT.md)

---

## Philosophen-Scraper
```bash
# 80+ Philosophen automatisch von Wikidata laden
npx ts-node scripts/scrape-wikidata.ts

# Einfluss-Netzwerk erkennen
npx ts-node scripts/detect-influences.ts
```

---

## Befehle

```bash
npm run dev          # Entwicklungsserver
npm run build        # Produktions-Build
npm run db:push      # Schema pushen
npm run db:seed      # Daten laden
npm run db:studio    # Prisma Studio
```

---

## Tech Stack

**Frontend:** Next.js 14 · TypeScript · Tailwind CSS · D3.js · SVG  
**Backend:** Node.js · PostgreSQL · Prisma ORM  
**KI:** Ollama (lokal) — llama3, mistral, phi4, gemma2, ...  
**Hosting:** Vercel · Supabase · GitHub Pages · Cloudflare Pages  
**Automatisierung:** Wikidata SPARQL · Wikipedia REST API · GitHub Actions

---

## Lizenz

MIT — frei nutzbar, veränderbar und teilbar.

---

*„Das Staunen ist der Anfang der Weisheit." — Platon*
