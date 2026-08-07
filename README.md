# Machine Learning — notebooks d'apprentissage

Notes prises en suivant la formation [Machine Learnia](https://www.youtube.com/@MachineLearnia),
réécrites avec mes propres explications, les pièges rencontrés en chemin, et des
exercices.

La numérotation reprend celle des vidéos, pour retrouver facilement la
correspondance.

**Dépôt en construction**, mis à jour au fil du parcours.

## Contenu

| Notebook | Sujet |
|---|---|
| 02 | Variables et fonctions |
| 14 | Matplotlib — les bases |
| 15 | Matplotlib — les graphiques du machine learning |
| 16 | SciPy — interpolation, optimisation, signal, images |
| 17 | Pandas — analyse du jeu de données Titanic |

À venir : structures de contrôle, listes et dictionnaires, NumPy, Seaborn,
scikit-learn.

## Ce que ces notebooks ajoutent au cours

Chaque notebook suit le même schéma : on écrit la version naïve, on regarde ce
qui cloche, on corrige. Les erreurs sont volontairement conservées, parce que
c'est en voyant un résultat raté qu'on comprend ce que fait chaque paramètre.

Une attention particulière est portée aux **erreurs silencieuses** — celles qui
ne lèvent aucun message et produisent un résultat crédible mais faux. Quelques
exemples documentés et vérifiés chiffres à l'appui :

- un `dropna` sur le Titanic qui fait grimper le taux de survie de deux points,
  parce que les âges manquants ne manquent pas au hasard
- un comptage d'objets sur une image qui en trouve 59 là où il y en a 24
- un calcul de fréquences par transformée de Fourier faux d'un facteur d'échelle,
  faute d'un paramètre optionnel
- une valeur par défaut mutable qui fait qu'une fonction se souvient de ses
  appels précédents

## Utilisation

```bash
git clone https://github.com/VOTRE_PSEUDO/machine-learning-notebooks.git
cd machine-learning-notebooks
pip install -r requirements.txt
jupyter notebook
```

Chaque notebook est autonome et s'exécute de haut en bas. Les cellules doivent
être lancées dans l'ordre : plusieurs sections réutilisent des variables
définies plus haut.

Le jeu de données Titanic se trouve dans `data/`. Les autres sont téléchargés
automatiquement par scikit-learn ou scikit-image.

## Sources

Formation suivie : [Machine Learnia](https://www.youtube.com/@MachineLearnia)
par Guillaume Saint-Cirgue.

Jeux de données : Iris et Breast Cancer via scikit-learn, Titanic
(données publiques), images de démonstration de scikit-image.

## Licence

MIT — voir le fichier `LICENSE`.
