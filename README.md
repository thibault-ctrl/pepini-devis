# Pepini Devis

Outil interne — Les Plantes d'Île-de-France.

## Déploiement

Hébergé sur GitHub Pages. Push = mise à jour automatique en quelques secondes.

## Architecture

- **Front** : `index.html` (statique) servi par GitHub Pages
- **Backend** : workflows n8n sur `https://planteidf.app.n8n.cloud`
  - `/webhook/pepini-devis` → matching IA des plantes
  - `/webhook/pepini-to-pennylane` → création devis Pennylane
  - `/webhook/rules` (GET) + `/webhook/rules-update` (POST) → règles métier
- **Données** : Supabase (catalogue 60k produits avec embeddings)

Aucune clé API n'est exposée côté navigateur — tout passe par n8n.
