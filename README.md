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

Le site Vercel sert un `index.html` minimal qui charge les deux artefacts
du dossier `deploy/` (polices et JS minifié) depuis jsDelivr, épinglés sur
un commit précis, avec repli sur `raw.githubusercontent.com`. Pour publier
une nouvelle version :

1. regénérer `deploy/game.min.js` à partir du script de `index.html`
   (`terser --compress --mangle`) ;
2. commit + push, relever le SHA ;
3. mettre à jour la constante `SHA` de la page déployée sur Vercel.

La page déployée doit reprendre le même remplissage `env(safe-area-inset-*)`
que le fichier canonique : en mode autonome sur iPhone, le contenu passe
sinon sous la barre d'état et l'en-tête des scores se retrouve caché par
l'heure et la batterie. Le jeu lit ce remplissage pour se dimensionner, donc
les deux doivent rester d'accord.

Le `index.html` à la racine reste la version canonique : un seul fichier
autonome, jouable hors ligne en l'ouvrant dans un navigateur.
