# releve-cli — Atelier Logiciel Nantais

`releve-cli` est un outil en ligne de commande conçu pour transformer un fichier de relevés au format CSV en un rapport de synthèse. Il s'adresse aux bénévoles et aux responsables de l'Atelier Logiciel Nantais qui doivent vérifier rapidement les mesures, la moyenne, le maximum et le minimum sans manipuler des feuilles de calcul.

## Architecture

Le projet est organisé autour de trois grandes responsabilités : la lecture du fichier de configuration, la lecture du fichier CSV de relevés, puis le calcul et l'affichage du rapport de synthèse. Ces blocs interagissent de manière simple et linéaire, ce qui rend le logiciel facile à comprendre et à maintenir dans un contexte d'atelier collaboratif.

Schéma détaillé : `docs/architecture.md` (produit en séance 3, pas encore présent).


## Organisation du dépôt

| Chemin | Contenu |
|---|---|
| `README.md` | Cette page : présentation, installation, usage, architecture. |
| `docs/reglages.md` | Référence des réglages disponibles. |
| `docs/demarrage.md` | Guide détaillé de démarrage. |
| `docs/architecture.md` | Schéma d'architecture détaillé (à venir, séance 3). |
| `CHANGELOG.md` | Journal des versions du projet. |
| `config.example.txt` | Modèle de configuration, sans valeur réelle. |

## Contact


Les commandes et les gestes de la plateforme sont résumés dans [l'aide-mémoire Git et GitHub](docs/aide-memoire-git-github.md).
La syntaxe Markdown utilisée dans toute la documentation est résumée dans [l'aide-mémoire Markdown](docs/aide-memoire-markdown.md).

Les gabarits de travail (fichier README complet, journal des versions, liste de contrôle de relecture,
compte rendu, schéma d'architecture, fiche de décision, fiche de lecture, tableau de répartition, grille de
revue, synthèse de revue, journal de traitement des retours, aide-mémoire des étiquettes) sont rassemblés
dans [`docs/modeles/`](docs/modeles/).
## Installation et démarrage

### Prérequis

Avant de démarrer, il faut disposer de :

 Python 3 installé ;
 une copie locale du dépôt ;
 un fichier de relevés au format CSV ;
 un éditeur de texte.

### Première utilisation

1 Copier le fichier de configuration d'exemple :

   ```bash
   cp config.example.txt config.txt
   ```

2 Ouvrir le fichier `config.txt` dans un éditeur de texte.

3 Renseigner le chemin du fichier de relevés avec le réglage `CHEMIN_RELEVES`.

4 Vérifier que le fichier de relevés indiqué existe.

5 Vérifier les autres paramètres nécessaires dans le fichier de configuration.

6 Lancer l'outil avec le fichier de configuration :

   ```bash
   python3 releve.py --config config.txt
   ```

### Résultat attendu

Le programme lit le fichier de relevés indiqué dans la configuration et produit un rapport de synthèse.

Le rapport permet notamment de consulter :

 le nombre de mesures ;
 la moyenne ;
 le maximum ;
 le minimum ;
 le signalement des doublons.

Pour plus d'informations sur les paramètres disponibles, consulter [docs/reglages.md](docs/reglages.md).

Pour consulter la procédure détaillée de démarrage, voir [docs/demarrage.md](docs/demarrage.md).

## Usage

### Modifier le fichier de relevés

Le fichier de relevés utilisé par `releve-cli` est indiqué dans le fichier `config.txt` avec le réglage `CHEMIN_RELEVES`.

Par exemple :

```text
CHEMIN_RELEVES=exemples/releves.csv
```

Après avoir renseigné le chemin du fichier, lancer :

```bash
python3 releve.py --config config.txt
```

L'outil utilise alors le fichier indiqué pour produire le rapport de synthèse.

### Modifier l'intervalle entre deux rapports

L'intervalle entre deux rapports peut être configuré avec le réglage `INTERVALLE`.

Par exemple :

```text
INTERVALLE=300
```

La valeur est exprimée en secondes.

Les différents réglages disponibles sont détaillés dans [docs/reglages.md](docs/reglages.md).

## Contribution

Les contributions sont réalisées sur une branche dédiée afin de séparer les différents sujets de travail.

Pour créer une branche :

```bash
git switch -c docs/nom-du-sujet
```

Les messages de commit doivent utiliser un préfixe permettant d'identifier le type de modification.

Pour une modification de documentation, utiliser le préfixe :

```text
docs:
```

Par exemple :

```text
docs: compléter le guide de démarrage
```

Avant de fusionner une modification dans la branche principale :

1 créer une branche dédiée au sujet ;
2 effectuer les modifications ;
3 créer un commit avec un message explicite ;
4 envoyer la branche sur GitHub ;
5 ouvrir une Pull Request ;
6 faire relire la modification par l'autre membre du binôme ;
7 répondre aux remarques éventuelles ;
8 fusionner la Pull Request après la relecture.

Cette organisation permet de conserver un historique clair des modifications et de favoriser la relecture croisée.
=======
Tom Caillaud et Emilien Pavageau — pour toute question, ouvrez une issue sur ce dépôt.
