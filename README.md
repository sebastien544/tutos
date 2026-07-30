# Tutos

Des tutos sous forme de checklist : on coche au fur et à mesure, l'app garde la place.

## Lancer

Double-cliquer sur `index.html`. Pour l'installer sur l'iPad, il faut passer par une
adresse web (GitHub Pages par exemple) : le manifeste et les icônes ne sont pris en
compte qu'en `http(s)`.

Tout est dans `index.html` : aucune dépendance, aucun serveur, aucun compte.

## Où sont les données

Dans le navigateur (`localStorage`) :

- `tutos.v1.custom` — les tutos écrits par toi
- `tutos.v1.progress` — les cases cochées, par tuto

Les quatre tutos fournis sont dans le fichier, pas dans le stockage : ils ne peuvent
pas être perdus, mais ils ne sont pas modifiables non plus. Le bouton **Dupliquer pour
modifier** en fait une copie qui, elle, t'appartient.

Effacer les données de site du navigateur efface les tutos écrits et la progression.
D'où le bouton **Exporter**, qui enregistre tout dans un `.json`, et **Importer**, qui
le relit et fusionne.

## Écrire un tuto

Dans le champ **Étapes** :

```
## Préparer le dossier          → une phase, pour regrouper
Créer le dossier du projet      → une ligne = une étape à cocher
  Un nom court, sans accent.    → deux espaces = précision de l'étape du dessus
```                             → un bloc de commande, copiable en un clic
git init
```
```

Le texte entre `backticks` s'affiche en code, et les adresses web deviennent des liens.

## Relier les tutos entre eux

Quand une étape renvoie à un tuto qui existe déjà, `[[double crochet]]` en fait un lien :

```
Télécharger l'image officielle
  Les vérifications sont détaillées dans [[Monter une image ISO]].
```

- Ce qui est entre crochets peut être **le titre ou l'identifiant** du tuto. Le titre est
  comparé sans tenir compte des accents, de la casse ni des espaces en trop, et un titre
  partiel suffit s'il ne désigne qu'un seul tuto.
- Le texte affiché est **toujours le vrai titre de la cible**. Renommer un tuto met donc
  tous les renvois à jour d'eux-mêmes.
- Un renvoi qui ne correspond à rien s'affiche en gris souligné de pointillés, avec
  « Aucun tuto ne porte ce nom » au survol. Rien ne casse, mais ça se voit.
- Un tuto ne se renvoie pas à lui-même : le titre s'affiche alors en texte simple.

En bas de chaque fiche, le bloc **Tutos liés** récapitule les deux sens : *Renvoie vers*
(les liens présents dans les étapes affichées) et *Cité par* (les tutos qui pointent
vers celui-ci). Le second sens est invisible autrement — c'est la raison d'être du bloc.
Il disparaît quand il n'y a rien à montrer.

## Replier les phases

L'en-tête de chaque phase est un bouton : un clic replie ou déplie ses étapes.
Le compteur (`4/6`) reste affiché même repliée, et passe au vert quand la phase est
finie. Le bouton **Tout replier** à côté des étiquettes agit sur toutes les phases.

Deux comportements automatiques, pour que le repli serve à quelque chose sans qu'on
ait à s'en occuper :

- À l'ouverture d'une fiche, **les phases entièrement cochées arrivent repliées**. Ce
  qui reste à faire est ce qu'on voit. Une fois dans la fiche, plus rien ne se replie
  tout seul : les plis sont à toi.
- Si l'étape en cours se retrouve dans une phase repliée, elle **se déplie** : la suite
  du travail n'est jamais cachée.

Les plis ne sont pas enregistrés. En quittant la fiche puis en revenant, ils se
recalculent à partir de ce qui est fait. **Tout décocher** redéplie tout.

## Les tutos à plusieurs versions

Un tuto fourni peut proposer plusieurs versions du même contenu — « Dépanner un
ordinateur qui rame » en a trois : Linux, Windows, macOS. Elles s'échangent par les
onglets sous la description.

- Chaque version a **sa propre progression** : cocher des étapes côté Linux ne touche
  pas à la version Windows. En stockage, la clé est `idDuTuto#idDeLaVersion`.
- L'onglet ouvert par défaut est celui du système sur lequel tu lis la page, puis celui
  que tu as regardé en dernier.
- L'adresse suit l'onglet (`#/t/b-lent/windows`), donc une version précise se met en
  favori ou se partage telle quelle.
- Un tuto ressort dans le filtre **En cours** dès qu'une seule de ses versions l'est, et
  la carte affiche alors cette version-là.

Ça ne concerne que les tutos fournis : l'éditeur crée des tutos à version unique, et
**Dupliquer pour modifier** copie la version affichée à ce moment-là.

## Bon à savoir

La case cochée est rattachée au **texte** de l'étape, pas à sa position. Réordonner
les étapes ou en insérer une nouvelle ne fait donc pas perdre la progression ;
réécrire le texte d'une étape, si.
