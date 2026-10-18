# Karom

Jeu de carrom arcade, jouable au doigt comme à la souris. Tout tient
dans un seul fichier `index.html` : moteur physique, rendu haute définition, interface cyan et orange, sons synthétisés.

## Design arcade

Plateau et logo 3D issus de la maquette validée, embarqués en WebP dans le HTML.
Le jeu reste autonome et fonctionne sans chargement réseau. Un plateau vectoriel
prend le relais pendant le décodage des images ; le marbre reste disponible.
Les pions utilisent des sprites calculés et mis en cache, avec tranches épaisses,
biseaux et ombres. Le rayon des pions passe de 16 à 27, le palet de 21 à 36 et
les trous de 20 à 40 unités. Les collisions utilisent ces mêmes dimensions.
Les six modes et leurs règles restent disponibles.

Commandes : placement avec la réglette, visée directement sur le plateau ou
avec le curseur, puissance réglable dans la jauge, bouton Tirer. Le déclenchement
au relâcher reste accessible dans les réglages. La pause se trouve en haut à droite.
Les préférences et records enregistrés sont conservés.

Validation Chromium : lancement depuis l'accueil, placement, visée, puissance,
tir et fin de mouvement, pause et reprise, six modes, thèmes et surfaces,
français et anglais, formats 390×844, 375×667 et 844×390. Aucune exception navigateur.

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

Langue (français ou anglais), déclenchement du tir (au relâcher ou au bouton),
revêtement du plateau (bois ou marbre), thème sombre ou clair, son. Les
réglages et les records de chaque mode sont conservés dans le navigateur.

Toute l'interface est traduite. Les textes vivent dans une seule table, chaque
entrée portant ses deux versions côte à côte : il devient impossible d'en
traduire une et d'oublier l'autre.

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

La page déployée doit reprendre le même remplissage haut
(`env(safe-area-inset-top)`) que le fichier canonique : en mode autonome sur
iPhone, le contenu passe sinon sous la barre d'état et l'en-tête des scores
se retrouve caché par l'heure et la batterie. Le jeu lit ce remplissage pour
se dimensionner, donc les deux doivent rester d'accord.

Le `index.html` à la racine reste la version canonique : un seul fichier
autonome, jouable hors ligne en l'ouvrant dans un navigateur.
