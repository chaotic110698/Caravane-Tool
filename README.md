# Les ateliers de Caravane

Les cinq outils d'auteur de [Caravane](https://github.com/chaotic110698/Caravane-2),
réunis sur une seule page pour les avoir sous la main partout — un téléphone, une
tablette, un ordinateur qui n'est pas le vôtre.

**→ [Ouvrir les ateliers](https://chaotic110698.github.io/Caravane-Tool/)**

| atelier | ce qu'on y écrit | ce qu'il exporte |
|---|---|---|
| [Carte](atelier-carte.html) | les lieux, les voies, les contrées, l'échelle | `monde.json` |
| [Personnages](atelier-personnages.html) | qui ils sont, et ce qu'on apprend d'eux à force | `personnages.json` |
| [Objets uniques](atelier-objets.html) | ce qu'ils font, d'où ils viennent, ce qu'ils cachent | `objets.json` |
| [Missions](atelier-missions.html) | qui les donne, ce qu'il faut faire, ce que ça rapporte | `missions.json` |
| [Événements](atelier-evenements.html) | une situation, un récit, deux à quatre issues | `evenements.json` |

Quatre modes d'emploi les accompagnent :
[événements](TUTORIEL-EVENEMENTS.md) ·
[personnages](TUTORIEL-PERSONNAGES.md) ·
[objets](TUTORIEL-OBJETS.md) ·
[missions](TUTORIEL-MISSIONS.md).

## Rien à installer

Chaque atelier est **un seul fichier HTML autonome** : le code, les catalogues et
les pictogrammes voyagent dedans. Aucune dépendance, aucun réseau une fois la page
ouverte, aucun compte. Ils fonctionnent aussi bien depuis GitHub Pages que par
double-clic sur le fichier téléchargé.

**Rien ne sort de votre machine.** Le travail en cours est gardé dans le navigateur,
atelier par atelier, et survit à la fermeture de l'onglet. Exportez quand même de
temps en temps : un navigateur qu'on nettoie emporte sa mémoire.

## Hors connexion

Ajoutez la page d'accueil à votre écran d'accueil — *Partager › Sur l'écran
d'accueil* sur iPhone, *⋮ › Installer* sur Android — et les cinq ateliers
s'ouvrent ensuite **sans réseau**. Un `sw.js` les met en cache à la première
visite, en préférant toujours le réseau quand il y en a, pour que vous ayez la
dernière version.

## Sur téléphone

Les quatre ateliers d'écriture montrent **une zone à la fois** : une barre en bas
passe de la liste à la fiche à l'aperçu, et les boutons se rangent dans le tiroir
**☰ Outils**.

L'atelier de carte garde la toile pour lui : les outils défilent en une rangée en
haut, le panneau se relève par sa poignée, et l'on se déplace à deux doigts. Il se
prête mieux à une tablette qu'à un téléphone — on y pose des points à la précision
du pixel.

## Ce qu'on fait des fichiers exportés

Ils se déposent dans le dossier `data/` du jeu, qui les lit tels quels. Ils sont
tous **facultatifs et indépendants** : posez-en un, le jeu s'en sert ; n'en posez
aucun, il tourne comme avant.

Une seule attention : le fichier des missions s'appelle là-bas
**`missions-ecrites.json`**, pour ne pas écraser le `missions.json` qui habille
déjà les contrats tirés au sort.

L'ordre qui évite les allers-retours : **la carte d'abord** (elle donne les clés de
lieu que tous les autres citent), puis les personnages, puis les objets et les
missions dans l'ordre qui vous arrange, les événements quand vous voulez.

## D'où vient ce dépôt

Ce n'est pas la source : les ateliers sont développés dans
[`Caravane-2/outils/`](https://github.com/chaotic110698/Caravane-2/tree/main/outils)
avec le jeu et les catalogues dont ils tirent leurs formulaires. Ici, ce sont les
fichiers **construits**, recopiés tels quels.

Pour publier une mise à jour, depuis `Caravane-2` :

```
node outils/construire.mjs                        # refait catalogues et tutoriels
node outils/exporter-ateliers.mjs ../Caravane-Tool
cd ../Caravane-Tool && git commit -am "Mise à jour des ateliers" && git push
```

Le hub (`index.html`), le manifeste, le cache et l'icône vivent ici et ne sont pas
touchés par la copie.

## Pour que le site s'affiche

Dans **Settings › Pages** de ce dépôt, choisissez la source **Deploy from a
branch**, branche `main`, dossier `/ (root)`. Une minute plus tard, l'adresse
ci-dessus répond.
