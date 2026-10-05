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

Tom Caillaud et Emilien Pavageau — pour toute question, ouvrez une issue sur ce dépôt.