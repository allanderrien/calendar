# Calendrier Luxembourg — CLAUDE.md

## Projet
Calendrier annuel luxembourgeois (2026–2028) en single-file HTML, hébergé sur GitHub Pages.
URL : https://allanderrien.github.io/calendar/
Repo : https://github.com/allanderrien/calendar

## Stack
- HTML/CSS/JS pur, zéro framework, zéro build
- Firebase Realtime Database pour la persistance multi-appareils
- Google Fonts : Syne + DM Mono

## Fichiers
- `index.html` — toute l'application (le seul fichier qui compte)
- `calendrier_2026.html` — ancienne version archivée, ne pas modifier

## Firebase
- Projet : `calendar-d8598`
- DB URL : `https://calendar-d8598-default-rtdb.europe-west1.firebasedatabase.app`
- Structure des données :
  - `/marked/YYYY-MM-DD` → `"conge"` | `"tele"` | `"recup"`
  - `/rdv/YYYY-MM-DD` → `{ client: "...", ville: "..." }`

## Fonctionnalités
- Sélecteur d'année : 2026 / 2027 / 2028
- Modes : ☀️ Congé · 💻 Télétravail · 🔄 Récup · 📍 RDV · 🗑 Effacer
- Raccourcis clavier : C / T / R / V / X
- KPI dashboard (jours restants par catégorie)
- Liste des RDV triée par date
- Export TSV pour Google Sheets
- Sync temps réel (dot vert = connecté)

## Valeurs par défaut
- Congés : 32 jours
- Télétravail : 34 jours
- Récup : 14 jours

## Jours fériés luxembourgeois
Calculés pour 2026 (Pâques 5 avril), 2027 (Pâques 28 mars), 2028 (Pâques 16 avril).

## Git
- Branche principale : `main`
- Email git configuré : `allanderrien@users.noreply.github.com` (privacy GitHub)
- GitHub Pages déployé depuis `main` / root
