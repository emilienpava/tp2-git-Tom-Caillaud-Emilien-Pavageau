# releve-cli — outil de synthèse de relevés

> Dépôt-modèle du module *Travail collaboratif & documentation technique* (Bachelor 2).
> Cliquez sur **Use this template** pour créer le dépôt de votre équipe, nommé
> `releve-cli-nom1-nom2`, puis invitez votre binôme comme collaborateur.

`releve-cli` est un petit outil en ligne de commande, développé et documenté en équipe. Il lit un
fichier de relevés au format CSV (des mesures horodatées) et produit un rapport de synthèse :
nombre de mesures, moyenne, maximum, minimum, et signalement des doublons.

## Démarrage

Avant la première utilisation, suivez le [guide de démarrage](docs/guide-demarrage.md).

## Configuration

Copiez `config.example.txt` sous le nom `config.txt` et complétez-le avec vos propres réglages.
Ne versionnez jamais `config.txt` : il est exclu par `.gitignore`.

## Contribuer

Toute modification passe par une branche dédiée et une PR décrite en trois parties (contexte,
changements, impact), relue par un membre de l'équipe qui n'a pas écrit la modification.

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
