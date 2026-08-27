# Machine Learning, notebooks d'apprentissage

Notes prises en suivant la formation [Machine Learnia](https://www.youtube.com/@MachineLearnia),
réécrites avec mes propres explications, les pièges rencontrés en chemin, et des
exercices.

La numérotation reprend celle des vidéos, pour retrouver facilement la
correspondance.

## Contenu

| Notebook | Sujet |
|---|---|
| 02 | Variables et fonctions |
| 03 | Structures de contrôle |
| 04 | Structures de données : listes et tuples |
| 05 | Dictionnaires |
| 06 | List comprehension |
| 07 | Built-in functions |
| 08 | Modules de base |
| 09 | Programmation orientée objet |
| 10 | NumPy : les bases |
| 11 | NumPy : indexing, slicing, boolean indexing |
| 12 | NumPy : maths et statistiques |
| 13 | NumPy : broadcasting |
| 14 | Matplotlib : les bases |
| 15 | Matplotlib : les graphiques du machine learning |
| 16 | SciPy : interpolation, optimisation, signal, images |
| 17 | Pandas : analyse du jeu de données Titanic |
| 18 | Pandas et séries temporelles |
| 19 | Seaborn |
| 20 | Scikit-learn : les bases |
| 21.0 | Scikit-learn : model selection |
| 21.1 | Scikit-learn : la validation croisée en détail |
| 21.2 | Scikit-learn : les métriques de régression |
| 22.0 | Scikit-learn : pre-processing |
| 22.1 | Scikit-learn : pipelines avancés et données hétérogènes |
| 22.2 | Scikit-learn : les imputers (valeurs manquantes) |
| 23 | Scikit-learn : feature selection |
| 24 | Scikit-learn : apprentissage non supervisé |
| 25 | Scikit-learn : ensemble learning |
| 27 | Projet COVID-19 : exploratory data analysis |
| 28 | Projet COVID-19 : prétraitement de données |
| 29 | Projet COVID-19 : modélisation |
| 30 | Exercices pratiques : Python, NumPy, Pandas, trading |

Les notebooks 27 à 29 forment un projet complet de bout en bout sur des
données médicales réelles (diagnostic du COVID-19, Hôpital Israelita Albert
Einstein) : de l'exploration des données brutes jusqu'au modèle final, en passant
par le nettoyage et l'optimisation.

## Ce que ces notebooks ajoutent au cours

Chaque notebook suit le même schéma : on écrit la version naïve, on regarde ce
qui cloche, on corrige. Les erreurs sont volontairement conservées, parce que
c'est en voyant un résultat raté qu'on comprend ce que fait chaque paramètre.

Une attention particulière est portée aux erreurs silencieuses celles qui
ne lèvent aucun message et produisent un résultat crédible mais faux. Quelques
exemples documentés et vérifiés chiffres à l'appui :

- un `dropna` sur le Titanic qui fait grimper le taux de survie de deux points,
  parce que les âges manquants ne manquent pas au hasard
- un comptage d'objets sur une image qui en trouve 59 là où il y en a 24
- un calcul de fréquences par transformée de Fourier faux d'un facteur d'échelle,
  faute d'un paramètre optionnel
- une valeur par défaut mutable qui fait qu'une fonction se souvient de ses
  appels précédents
- une fuite d'information silencieuse quand on normalise avant de séparer
  train et test le score paraît excellent, puis s'effondre en production

Chaque notebook se termine par un mémo récapitulatif et des exercices
corrigés séparément.

## Le fil rouge : éviter les fuites d'information

À partir du notebook 21, un thème traverse tout le cours : garantir des
évaluations honnêtes. Séparer train et test avant tout nettoyage, mettre chaque
étape qui apprend des données (mise à l'échelle, imputation, sélection de
variables) à l'intérieur d'un pipeline, et ne jamais laisser le jeu de test
influencer la préparation. C'est ce qui distingue un score affiché d'un score
réel.

## Utilisation

​```bash
git clone https://github.com/badaouihakimou/machine-learning-notebooks.git
cd machine-learning-notebooks
pip install -r requirements.txt
jupyter notebook
​```

Chaque notebook est autonome et s'exécute de haut en bas. Les cellules doivent
être lancées dans l'ordre : plusieurs sections réutilisent des variables
définies plus haut.

Le jeu de données Titanic se trouve dans `data/`. Les jeux Iris, Digits, Diabetes
et Breast Cancer sont téléchargés automatiquement par scikit-learn. Le jeu
COVID-19 des notebooks 27 à 29 est disponible sur
[Kaggle](https://www.kaggle.com/datasets/einsteindata4u/covid19) et doit être
téléchargé séparément (`dataset.xlsx`).

## Sources

Formation suivie : [Machine Learnia](https://www.youtube.com/@MachineLearnia)
par Guillaume Saint-Cirgue.

Jeux de données : Iris, Digits, Diabetes et Breast Cancer via scikit-learn ;
Titanic (données publiques) ; images de démonstration de scikit-image ; dataset
COVID-19 de l'Hôpital Israelita Albert Einstein via Kaggle.

## Licence

MIT : voir le fichier `LICENSE`.
