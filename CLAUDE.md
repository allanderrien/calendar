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
  - `/quotas/YYYY` → `{ conge, recup, tele, report }` (plafonds propres à chaque année ; `report` saisi uniquement pour 2026)
  - `/birthdays/MM-DD` → `{ nom: "..." }` (récurrent chaque année)

## Fonctionnalités
- Sélecteur d'année : 2026 / 2027 / 2028
- Modes : ☀️ Congé · 💻 Télétravail · 🔄 Récup · 📍 RDV · 🎂 Anniversaires · 🗑 Effacer
- Raccourcis clavier : C / T / R / V / B / X
- Anniversaires : contour rose extérieur sur le jour, liste dédiée, colonne dans l'export
- KPI dashboard (jours restants par catégorie, année affichée, jours ouvrés uniquement)
- Liste des RDV triée par date
- Export TSV pour Google Sheets
- Sync temps réel (dot vert = connecté)

## Report de congés
- Report de l'année n-1 = restants de n-1 (plafond + report conservé − posés), plafonné à 10 jours.
- Les jours reportés sont à poser avant le 1er mai ; non posés à cette date (comparée à la date du jour), ils sont déduits de la réserve.
- Affichage : « X utilisés / plafond + Y reportés ». 2026 n'a pas d'année n-1 : le report se saisit à la main.

## Valeurs par défaut (modifiables année par année, enregistrées dans Firebase)
- Congés : 32 jours
- Télétravail : 34 jours
- Récup : 14 jours

## Jours fériés luxembourgeois
Calculés pour 2026 (Pâques 5 avril), 2027 (Pâques 28 mars), 2028 (Pâques 16 avril).
Inclut la Journée de l'Europe (9 mai), férié légal depuis 2019.

## Git
- Branche principale : `main`
- Email git configuré : `allanderrien@users.noreply.github.com` (privacy GitHub)
- GitHub Pages déployé depuis `main` / root
