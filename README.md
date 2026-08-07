# Les ateliers de Caravane

Les six outils d'auteur de [Caravane](https://github.com/chaotic110698/Caravane-2),
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
| [Icônes](atelier-icones.html) | un symbole en six formes, et sa couleur | `icones.json` |

Cinq modes d'emploi les accompagnent :
[événements](TUTORIEL-EVENEMENTS.md) ·
[personnages](TUTORIEL-PERSONNAGES.md) ·
[objets](TUTORIEL-OBJETS.md) ·
[missions](TUTORIEL-MISSIONS.md) ·
[icônes](TUTORIEL-ICONES.md).

## Un seul dépôt pour les six

Les ateliers **partagent leur travail**. La carte que vous tracez, l'atelier de
personnages la connaît sans qu'on lui porte un fichier ; les personnages que vous
écrivez, l'atelier de missions les propose déjà dans son onglet **Personnages** ;
une icône dessinée apparaît aussitôt dans les listes de dessins de tous les
autres. Le bouton *Ouvrir un fichier* ne sert plus qu'à reprendre un travail venu
d'ailleurs.

La page d'accueil porte un **codex** : tout ce que vous avez écrit, rangé par
catégorie, avec un bouton qui rouvre chaque élément dans l'outil qui l'a fait.

## Emporter son travail

Deux boutons sur la page d'accueil, et deux besoins différents.

**Tout sauvegarder** produit un `caravane-atelier-AAAA-MM-JJ.json` qui contient tout —
le monde, les gens, les objets, les missions, les événements, les icônes, et jusqu'à
l'élément que vous aviez ouvert dans chaque outil. C'est le fichier qui passe de
l'ordinateur au téléphone. **Reprendre une sauvegarde** le relit, montre d'abord ce
qu'il contient, puis vous laisse choisir : *fusionner* (à clé égale la sauvegarde
l'emporte, et ce qu'elle ignore reste) ou *tout remplacer*.

L'image de fond de la carte n'y voyage pas — trop lourde pour un JSON. Redéposez-la sur
l'autre appareil, les lieux retomberont dessus.

**Les fichiers du jeu**, en dessous, sortent une section à la fois sous le nom exact que
`data/` attend. Rien n'oblige à tout finir avant de livrer : une liste de missions seule
est un fichier valable.

## Rien à installer

Chaque atelier est **un seul fichier HTML autonome** : le code, les catalogues et
les pictogrammes voyagent dedans. Aucune dépendance, aucun réseau une fois la page
ouverte, aucun compte. Ils fonctionnent aussi bien depuis GitHub Pages que par
double-clic sur le fichier téléchargé.

**Rien ne sort de votre machine.** Le travail en cours est gardé dans le navigateur,
dans un dépôt que les six ateliers partagent, et survit à la fermeture de l'onglet.
Exportez quand même de temps en temps : un navigateur qu'on nettoie emporte sa
mémoire.

## Hors connexion

Ajoutez la page d'accueil à votre écran d'accueil — *Partager › Sur l'écran
d'accueil* sur iPhone, *⋮ › Installer* sur Android — et les six ateliers
s'ouvrent ensuite **sans réseau**. Un `sw.js` les met en cache à la première
visite, en préférant toujours le réseau quand il y en a, pour que vous ayez la
dernière version.

## Sur téléphone

Les cinq ateliers d'écriture montrent **une zone à la fois** : une barre en bas
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

Le manifeste, le cache et l'icône sont recopiés eux aussi ; seul ce README
appartient à ce dépôt-ci et n'est jamais touché par la copie.

## Pour que le site s'affiche

Dans **Settings › Pages** de ce dépôt, choisissez la source **Deploy from a
branch**, branche `main`, dossier `/ (root)`. Une minute plus tard, l'adresse
ci-dessus répond.
