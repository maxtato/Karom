# Icône de l'application

Le visuel vient de toi (`source-1254.png`, 1254×1254) : le palet vert et le
jeton clair au moment du choc, gerbe dorée entre les deux, lignes de vitesse
derrière chacun, sur le plateau de bois.

## Sur la définition

La source fait 1254 px de côté — plus que les 1024 px de la plus grande
taille demandée par les systèmes. **Aucun agrandissement n'était donc
nécessaire**, et il aurait été contre-productif : l'image a été
rééchantillonnée avant de m'arriver (54 709 couleurs distinctes, dix
ruptures franches seulement sur toute la largeur), autrement dit ses blocs
sont flous. L'agrandir n'aurait fait qu'étaler ce flou.

Toutes les tailles sont donc obtenues par **réduction**, ce qui resserre les
blocs et masque le flou. Sous 256 px la réduction se fait en deux temps
(1254 → 512 → cible) : un seul saut bavait.

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

## Si tu veux du vraiment net

Je peux redessiner cette composition exacte — même palet, même jeton, même
gerbe, mêmes lignes de vitesse — avec les primitives pixel du jeu. Le
résultat serait tracé sur une grille franche et resterait net à n'importe
quelle taille, au lieu d'être une réduction d'une image floue.
