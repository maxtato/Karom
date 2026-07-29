# Icône de l'application

Le visuel vient de toi (`source-1254.png`, 1254×1254) : le palet vert et le
jeton clair à l'instant du choc, gerbe dorée entre les deux, lignes de
vitesse derrière le palet, le tout sur un plateau de bois vu en entier —
cadre sombre, coins renforcés, tapis clair veiné. Le format est carré et à
fond perdu, c'est ce qu'il faut : les systèmes appliquent eux-mêmes leur
masque arrondi.

Cette version-ci corrige les angles : le cadre est rentré de quelques pixels
et ses coins intérieurs sont arrondis, si bien que le masque du système
retombe sur la courbe du plateau au lieu de couper le bois en biais.

## Sur la définition

La source fait 1254 px de côté, soit plus que les 1024 px de la plus grande
taille réclamée par les systèmes. **Aucun agrandissement n'était donc
nécessaire**, et il aurait été contre-productif : l'image a été
rééchantillonnée avant de m'arriver — 74 605 couleurs distinctes et
seulement 26 ruptures franches sur toute la largeur, là où un vrai pixel art
compte quelques dizaines de couleurs et une rupture à chaque bord de bloc.
Autrement dit ses blocs sont légèrement flous, et l'agrandir n'aurait fait
qu'étaler ce flou sans ajouter le moindre détail.

Toutes les tailles viennent donc d'une **réduction**, qui resserre les blocs
et fait disparaître le flou. Sous 256 px la réduction se fait en deux temps
(1254 → 512 → cible) : un saut unique bavait.

| Fichier | Usage |
|---------|-------|
| `icone-1024.png` | master, magasins d'applications |
| `icone-512.png` | manifeste web, écran de démarrage Android |
| `icone-192.png` | manifeste web, écran d'accueil Android |
| `icone-180.png` | `apple-touch-icon`, iPhone |
| `icone-167.png` | iPad Pro |
| `icone-152.png` | iPad |
| `icone-120.png` | iPhone ancien |
| `icone-32.png` | onglet du navigateur |

`apercu-accueil.png` montre le rendu à 160, 80, 60 et 40 px avec le masque
arrondi : c'est le vrai test de lisibilité.

## Câblage

Ce visuel sert **à la fois** d'icône d'application et de logo du site :

- **écran d'accueil du téléphone** : `manifest.webmanifest` (nom, affichage
  autonome, orientation portrait, couleurs de fond et de thème) plus les
  quatre `apple-touch-icon` d'iOS ;
- **onglet du navigateur** : les favicons 32 et 192 px, qui remplacent le
  petit plateau SVG dessiné en ligne jusqu'ici ;
- **aperçu des liens partagés** : `og:image` et `twitter:image` en 512 px,
  avec une carte de type `summary` — carrée, comme le visuel.

Les fichiers sont servis par jsDelivr, épinglés sur un commit — le même
mécanisme que le jeu lui-même.

Le `index.html` à la racine du dépôt reste autonome et garde son favicon SVG
en ligne : il doit fonctionner hors ligne, sans dépendre d'un réseau.

## Si tu veux du vraiment net

Je peux redessiner cette composition exacte — même palet, même jeton, même
gerbe, mêmes lignes de vitesse — avec les primitives pixel du jeu. Elle
serait alors tracée sur une grille franche et resterait nette à n'importe
quelle taille, au lieu d'être la réduction d'une image légèrement floue.
