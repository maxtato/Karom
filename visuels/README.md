# Pistes d'icône

Sept propositions pour l'icône de l'application, dessinées dans le style du
jeu : mêmes couleurs, mêmes primitives pixel, même rosace que le centre du
plateau. Chaque fichier est un master de 1024×1024, tracé sur une grille de
128 puis agrandi huit fois au plus proche voisin — les pixels restent francs
à toutes les tailles.

| # | Fichier | Ce que ça raconte |
|---|---------|-------------------|
| 1 | `icone-1-plateau.png` | Le plateau vu de dessus : cadre, tapis, quatre trous, rosace, pastilles rouges. Le plus explicite. |
| 2 | `icone-2-reine.png` | La reine rouge posée sur la rosace. Lecture immédiate en petit. |
| 3 | `icone-3-palet.png` | Le palet vert, l'objet que l'on lance. Le plus simple. |
| 4 | `icone-4-monogramme.png` | Un K en Jersey sur bois, avec les trois jetons. |
| 5 | `icone-5-jetons.png` | Les trois jetons du jeu : clair, foncé, reine. |
| 6 | `icone-6-tir.png` | Le palet vise un jeton, trajectoire pointillée entre les deux. La paire est centrée dans le cadre. |
| 7 | `icone-7-rosace.png` | La rosace seule, plein cadre. Emblème abstrait. |

- `planche.png` — les sept côte à côte, en grand
- `apercu-accueil.png` — les sept à taille réelle sur un écran d'accueil,
  coins arrondis compris : c'est le vrai test de lisibilité
- `icones.html` — la source, pour retoucher une piste et régénérer

## Régénérer

`icones.html` charge les polices depuis `../deploy/fonts.css` : ouvrir le
fichier dans un navigateur suffit. Chaque canvas `#bigN` porte le master
1024×1024, récupérable par `toDataURL()`.

## Ce qu'il reste à faire pour une vraie icône d'application

Une fois la piste choisie : déclarer un manifeste web (`manifest.webmanifest`)
avec les tailles 192 et 512, plus une balise `apple-touch-icon` de 180×180
pour iOS. Le jeu deviendra alors installable depuis le navigateur, avec son
icône sur l'écran d'accueil et sans barre d'adresse.
