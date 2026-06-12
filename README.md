# Site de vente — Solune

`index.html` est une **landing page autonome** (un seul fichier, aucune dépendance, aucun build). Hébergeable partout.

## Mode actuel : PRÉ-LANCEMENT (capture d'emails)
Les boutons pointent vers une **liste d'attente** (`#waitlist`) — un formulaire **Netlify Forms** (gratuit, aucun backend). Une fois la page **hébergée sur Netlify** (voir plus bas), les emails arrivent dans **Netlify → Forms**. (Si tu héberges ailleurs, branche [Formspree](https://formspree.io) ou [Tally](https://tally.so) à la place — change l'attribut du `<form>`.)

## Au LANCEMENT — passer de waitlist à vente (3 choses)
1. **Lien d'achat** : dans `index.html`, le lien Gumroad/Lemon Squeezy est en commentaire au-dessus du bouton `#pricing`. Remets le bouton « Obtenir Solune » avec ton vrai lien, et repointe les CTA (`href="#waitlist"` → ton lien) si tu veux vendre directement.
2. **Prix** : remplace `—€` (section `#pricing`) par ton prix (ex. `39€` early-bird).
3. **Specs** (optionnel) : ajuste la config Mac minimale (section `#how`).

## Aperçu en local
```bash
cd landing && python3 -m http.server 4173
# puis ouvre http://localhost:4173
```

## Mettre en ligne (gratuit)
- **Netlify Drop** : glisse le dossier `landing/` sur https://app.netlify.com/drop → en ligne en 10 s.
- **Vercel** : `npx vercel landing/`.
- **GitHub Pages** : pousse `landing/` et active Pages sur le dossier.
- **Cloudflare Pages** : connecte le repo, dossier de sortie `landing`.

## Vendre (encaisser)
- **Gumroad** (le plus simple) : crée un produit « Solune », téléverse le `.dmg`, récupère le lien, colle-le dans la page. Gumroad gère paiement + livraison du fichier.
- **Lemon Squeezy** : idem, meilleure gestion TVA/licences si tu veux des clés de licence (le projet a déjà un système de licence Ed25519).

## Démo vidéo
Le script est prêt dans [`../docs/VIDEO_DEMO_SCRIPT.md`](../docs/VIDEO_DEMO_SCRIPT.md). Enregistre l'écran (QuickTime/ScreenStudio) en suivant le script : « Hey Solune », une question, une demande de code, la vision caméra, l'argument 100% local.

## Cohérence des promesses
La page ne promet QUE ce qui est vérifié par les tests (`tests/full_capability_test.py`, `tests/deep_promises_test.py`) : voix « Hey Solune », vision, code, mémoire, contrôle Mac, recherche web, 100% local, chiffrement. Ne rajoute pas de promesse non tenue.
