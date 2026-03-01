# 🚀 ASIO Growth Platform — v3

> SPA de marketing para ASIO Marketing. Versión de alta performance sin frameworks pesados.
> Desarrollado como MVP para entrevista técnica + propuesta de migración frontend.

![Deploy](https://img.shields.io/badge/Deploy-Netlify-00C7B7?logo=netlify)
![Stack](https://img.shields.io/badge/Stack-Vanilla%20JS%20%2B%20CSS-orange)
![AI](https://img.shields.io/badge/AI-Gemini%202.0%20Flash-blue)

---

## ⚡ Stack

| Layer | Tecnología |
|---|---|
| Frontend | HTML5 + CSS3 (100% keyframes, zero Framer Motion) |
| Estilos | Tailwind CDN (standalone) |
| AI | Gemini 2.0 Flash via proxy seguro |
| Deploy | Netlify (Functions + CDN) |
| Fonts | Syne (display) + DM Sans (body) |

---

## 📁 Estructura

```
asio-growth-platform/
├── public/
│   └── index.html          # SPA completa — 3 vistas (#home, #mastery, #bank)
├── netlify/
│   └── functions/
│       └── gemini.js       # Proxy seguro — GEMINI_API_KEY nunca al cliente
├── netlify.toml            # Redirects + Headers de seguridad + Cache
├── .gitignore
└── README.md
```

---

## 🔐 Variables de entorno

Configurar en **Netlify Dashboard → Site → Environment Variables**:

| Variable | Descripción |
|---|---|
| `GEMINI_API_KEY` | API Key de Google AI Studio |

**Obtener key**: https://aistudio.google.com/app/apikey

---

## 🚀 Deploy

### Netlify (recomendado)
```bash
# 1. Conectar repo en Netlify Dashboard → Add new site → Import from GitHub
# 2. Build settings: publish = public (ya configurado en netlify.toml)
# 3. Agregar GEMINI_API_KEY en Environment Variables
# 4. Deploy
```

### Local
```bash
# Instalar Netlify CLI
npm install -g netlify-cli

# Crear .env con tu key
echo "GEMINI_API_KEY=tu_key_aqui" > .env

# Correr localmente con Functions
netlify dev
```

---

## 🎯 Features

### ✅ Implementado
- **SPA Hash Router** — `#home`, `#mastery`, `#bank` con `history.pushState` limpio
- **NanoBot v3.0** — Chat AI con handoff a WhatsApp (`[HANDOFF]`) y retry exponencial
- **Meta Ads Generator** — 3 copies por generación via Gemini, con Copy button
- **Ecosystem Section** — Partners, Affiliate, Webinars, Blog (4 cards)
- **Scroll Reveal** — IntersectionObserver, 12 @keyframes, stagger en grids
- **Community Tags** — Bounce escalonado 60ms por tag
- **Pricing Config** — Centralizado en `PRICING_CONFIG` JS object
- **SEO** — og:title, og:image, Twitter Card, canonical, favicon

### 🔒 Seguridad
- API Key via env var, nunca expuesta al cliente
- CSP headers en netlify.toml
- X-Frame-Options DENY

### 📊 Performance vs sitio original
| Métrica | Original (React/Next.js) | v3 (Vanilla) |
|---|---|---|
| Bundle animaciones | ~90KB (Framer Motion) | 0KB |
| Image requests hero | 15 individuales | 0 (CSS gradients) |
| DOM duplicado | Sí (marquees JS) | No (CSS puro) |
| TBT estimado | +400-600ms | <50ms |

---

## 📌 Roadmap

- [ ] Migración a Astro 4 (monorepo)
- [ ] Neon Postgres para datos persistentes
- [ ] Stripe para pagos Mastery
- [ ] MailerLite para registro de webinars
- [ ] Meta Pixel + GTM (requiere IDs del cliente)
- [ ] ARIA AI Agent (ASIO Research & Intelligence Agent)

---

## 👤 Desarrollado por

**JAJA_DEV** (Julián Alexander Juárez Alvarado)
Jefe de Sistemas · Full-Stack Developer · UNT TEAM

> *"Performance first. Zero frameworks where CSS wins."*
