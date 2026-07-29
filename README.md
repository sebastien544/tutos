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

## Bon à savoir

La case cochée est rattachée au **texte** de l'étape, pas à sa position. Réordonner
les étapes ou en insérer une nouvelle ne fait donc pas perdre la progression ;
réécrire le texte d'une étape, si.
