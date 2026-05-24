# aleks.bechter — Persönliche Website

Single-Page Site für Aleksander Bechter mit Sub-Seiten für seine Apps.

## Struktur

```
aleks-site/
├── index.html                      # Hauptseite
├── apps/
│   ├── buchungssaetze.html         # Beschreibung der App
│   └── buchungssaetze_quiz.html    # Das eigentliche Quiz
└── README.md
```

## Was du noch ergänzen musst

### 1. Aleks' Foto einfügen (im index.html)

Aktueller Code (in der `<div class="hero-photo">` Sektion):
```html
<div class="hero-photo">
  <div class="hero-photo-placeholder">AB</div>
</div>
```

Sobald du das Foto hast, ersetze die Zeile mit dem Placeholder durch:
```html
<div class="hero-photo">
  <img src="aleks.jpg" alt="Aleksander Bechter">
</div>
```

Foto-Empfehlungen:
- Quadratisch zugeschnitten (sonst Verzerrung)
- Mindestens 500×500 px, max 1000×1000 px für gute Ladezeit
- JPG oder WebP, unter 200 KB

### 2. LinkedIn-URL einfügen (sobald vorhanden)

In `index.html` die LinkedIn-Card unkommentieren und URL einfügen.

## Deployment auf Firebase Hosting

### Voraussetzungen
- Node.js installiert
- Firebase Account verbunden
- Domain bereits gekauft (z.B. aleks-bechter.at)

### Schritt-für-Schritt

```bash
# 1. Firebase CLI installieren
npm install -g firebase-tools

# 2. Login
firebase login

# 3. Im Projektordner initialisieren
cd aleks-site
firebase init hosting

# Bei Setup-Wizard:
# - Use an existing project ODER Create new
# - Public directory: . (Punkt — aktueller Ordner)
# - Single-page app: NO
# - GitHub Actions: optional (empfohlen JA für Auto-Deploy)

# 4. Deploy!
firebase deploy --only hosting

# Test-URL kommt raus: https://aleks-bechter.web.app
```

### Custom Domain anbinden

1. In Firebase Console → Hosting → "Add custom domain"
2. Domain eingeben: aleks-bechter.at
3. DNS A-Records bei deinem Domain-Provider eintragen
4. SSL wird automatisch erstellt (Let's Encrypt, ca. 30 Min)

## Alternative: GitHub Pages

```bash
cd aleks-site
git init
git add .
git commit -m "Initial site"

# Repo auf GitHub erstellen, dann:
git remote add origin https://github.com/7bechti9/aleks-bechter.git
git branch -M main
git push -u origin main

# Auf GitHub: Settings → Pages → Source: main branch / root
# URL: https://7bechti9.github.io/aleks-bechter/
```

## Lokal testen

Einfach `index.html` mit Doppelklick öffnen — oder besser:

```bash
# Python-Server (immer verfügbar)
cd aleks-site
python3 -m http.server 8000
# Öffnen: http://localhost:8000
```
