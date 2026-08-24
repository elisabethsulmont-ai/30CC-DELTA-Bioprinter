# 3D files

```
stl/       pièces à imprimer, prêtes à trancher
sources/   fichiers Rhino éditables (.3dm) et exports .step
```

Une STL ne se modifie pas. Publier uniquement des STL, c'est publier une machine que
personne ne peut adapter. Mets les sources Rhino à côté, et si tu peux, un export **.step**
par pièce, lisible par tous les logiciels de CAO.

## Ce qui vient de ton disque

Depuis `02_HARDWARE/EXPORT STL/` :

> **Attention, ce dossier mélange deux choses** : des pièces de la machine
> (`Clamp*.stl`, `KNOB.stl`, `Spanner.stl`, `1/2/3.stl`, `V2/v3.stl`) et des objets
> imprimés qui sont ton travail artistique (`metaball_geodesic.stl`,
> `test_space_colonization.stl`, `test_converge.stl`, `PRINT TEST 1.stl`…).
> Seules les pièces de la machine ont leur place ici. Les autres relèvent d'une publication
> différente, si tu la veux.

Depuis `02_HARDWARE/` : `_Whole_Printer_v14.3dm`, `LEVITATEUR.3dm`, `SOCLE.3dm`.

## Poids des fichiers, à régler avant le premier push

GitHub refuse tout fichier de plus de **100 Mo** et avertit au-delà de **50 Mo**.

| Fichier | Taille | |
|---|---|---|
| `LEVITATEUR.3dm` | ~71 Mo | passe, mais déclenche un avertissement |
| `_Whole_Printer_v14.3dm` | ~58 Mo | idem |

Trois options, de la plus simple à la plus propre :

1. Purger les `.3dm` dans Rhino avant export (`_Purge`, supprimer l'historique et les blocs
   inutilisés), ce qui fait souvent chuter la taille de moitié.
2. Exporter une pièce par fichier plutôt qu'un seul fichier machine entière.
3. Activer **Git LFS** pour les `.3dm` et les `.stl`. Efficace, mais ajoute une dépendance
   pour qui clone le dépôt.

Ne mets pas `02_HARDWARE/OLD/` dans le dépôt. L'historique des versions, c'est le rôle de
Git, pas celui d'un dossier.

## Table des pièces

<!-- TODO : une ligne par pièce imprimée -->

| Fichier | Pièce | Qté | Matériau | Remarques |
|---|---|---|---|---|
| | | | | |
