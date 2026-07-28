# Karom

Jeu de carrom en pixel art, jouable au doigt comme à la souris. Tout tient
dans un seul fichier `index.html` : moteur physique, rendu pixel, polices
embarquées, sons synthétisés.

## Modes de jeu

- **Classique** — les règles du carrom : 9 jetons par camp, la reine à couvrir.
- **Partie rapide** — 5 jetons, règles adoucies.
- **Points** — aucune couleur attitrée, cible 15 points.
- **Nettoyage** — vider le plateau en 20 tirs, 3 étoiles à décrocher.
- **Combo** — chaque jeton de plus dans le même tir double la mise.
- **Contre la montre** — 2 minutes, chaque jeton rend 4 secondes.

Seul contre l'ordinateur (3 niveaux) ou à deux sur le même écran, le plateau
pivote entre les tours.

## Réglages

Déclenchement du tir (au relâcher ou au bouton), thème sombre ou clair,
son. Les réglages et les records de chaque mode sont conservés dans le
navigateur.

## Développement

Aucune dépendance, aucun build : ouvrir `index.html` dans un navigateur.

## Déploiement

Site statique, déployé sur Vercel tel quel.
