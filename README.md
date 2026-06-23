# 🕷 SpiderScann v3.0
**Outil de Diagnostic Réseau Professionnel + IA GPT-4o**
*by Anony'x — +226 03 99 64 69*

---

## 📦 Structure du projet

```
spiderscann/
├── server.js          ← Backend Node.js (API réseau + IA)
├── package.json       ← Dépendances
├── README.md          ← Ce fichier
└── public/
    └── index.html     ← Frontend complet
```

---

## 🚀 Lancement en local

```bash
# 1. Installer les dépendances
npm install

# 2. Ajouter ta clé OpenAI (IMPORTANT)
# Sur Windows:
set OPENAI_API_KEY=sk-...ta-clé...

# Sur Mac/Linux:
export OPENAI_API_KEY=sk-...ta-clé...

# 3. Lancer le serveur
node server.js

# 4. Ouvrir dans le navigateur
# http://localhost:3000
```

---

## 🌐 Déploiement GitHub + Render

### Étape 1 — GitHub
1. Créer un repo `spiderscann` sur github.com
2. Uploader les fichiers :
   - `server.js` → à la racine
   - `package.json` → à la racine
   - `README.md` → à la racine
   - `public/index.html` → dans le dossier `public/`

### Étape 2 — Render
1. Aller sur render.com → **New Web Service**
2. Connecter le repo GitHub `spiderscann`
3. Configurer :
   - **Build Command:** `npm install`
   - **Start Command:** `node server.js`
   - **Plan:** Free
4. Ajouter la variable d'environnement :
   - **Key:** `OPENAI_API_KEY`
   - **Value:** `sk-...ta-nouvelle-clé...`
5. Cliquer **Create Web Service**

### Étape 3 — Connecter le frontend
Dans `public/index.html`, ligne `const API = '';`
Remplacer par :
```js
const API = 'https://spiderscann.onrender.com';
```
Puis re-uploader `index.html` sur GitHub.

### Étape 4 — BetterStack (anti-sleep)
1. Aller sur betterstack.com → Uptime → New Monitor
2. URL: `https://spiderscann.onrender.com/api/health`
3. Fréquence: **Every 5 minutes**
→ Empêche Render de mettre le serveur en veille.

---

## 🔧 Routes API

| Route | Méthode | Description |
|-------|---------|-------------|
| `/api/health` | GET | Statut serveur |
| `/api/hosts` | POST | Host Checker TCP |
| `/api/ports` | POST | Port Scanner TCP |
| `/api/dns` | GET | DNS Lookup natif |
| `/api/ping` | GET | Ping & Latence |
| `/api/geoip` | GET | GeoIP Info |
| `/api/ssl` | GET | SSL/TLS Check |
| `/api/whois` | GET | WHOIS/RDAP |
| `/api/ai/hosts` | POST | IA analyse hosts |
| `/api/ai/ports` | POST | IA analyse ports |
| `/api/ai/dns` | POST | IA analyse DNS |
| `/api/ai/ssl` | POST | IA analyse SSL |
| `/api/ai/ping` | POST | IA analyse ping |
| `/api/ai/whois` | POST | IA analyse WHOIS |
| `/api/ai/geoip` | POST | IA analyse IP |
| `/api/ai/chat` | POST | Chat IA libre |

---

## 🛠 Fonctionnalités

### 🌐 Online (Serveur Node.js — TCP réel)
- ✅ Host Checker + Analyse IA
- ✅ Port Scanner TCP + Analyse sécurité IA
- ✅ DNS Lookup natif + Analyse IA
- ✅ GeoIP + Analyse IA
- ✅ SSL/TLS + Analyse IA
- ✅ Ping TCP + Analyse IA
- ✅ WHOIS/RDAP + Analyse IA
- ✅ Chat IA libre (GPT-4o)

### 📡 Offline (100% navigateur)
- ✅ Calculateur CIDR/Sous-réseau
- ✅ Analyseur IP
- ✅ Encodeur Base64/URL/Hex
- ✅ Hash SHA-256/512
- ✅ Référence 28+ ports TCP

---

## 🔐 Sécurité de la clé API
La clé OpenAI est stockée en variable d'environnement sur Render.
Elle ne figure **jamais** dans le code source — repo GitHub public sans risque.

---

## 👨‍💻 Créateur
**Anony'x** — Développeur · Burkina Faso 🇧🇫
📱 WhatsApp: +226 03 99 64 69
