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
