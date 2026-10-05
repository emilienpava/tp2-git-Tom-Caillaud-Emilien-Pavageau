# Démarrage de releve-cli

## Prérequis

Avant de démarrer, il faut disposer de :

* Python 3 installé ;
* une copie locale du dépôt ;
* un fichier de relevés au format CSV ;
* un éditeur de texte.

## Première utilisation

1. Cloner le dépôt de l'équipe, puis se placer dans le dossier du projet.

2. Copier le fichier de configuration d'exemple :

   ```bash
   cp config.example.txt config.txt
   ```

3. Ouvrir le fichier `config.txt` dans un éditeur de texte.

4. Renseigner le chemin du fichier de relevés avec le réglage `CHEMIN_RELEVES`.

   Exemple :

   ```text
   CHEMIN_RELEVES=exemples/releves.csv
   ```

5. Vérifier que le fichier de relevés indiqué existe.

6. Vérifier les autres paramètres nécessaires dans le fichier de configuration.

7. Lancer l'outil avec le fichier de configuration :

   ```bash
   python3 releve.py --config config.txt
   ```

## Résultat attendu

Le programme lit le fichier de relevés indiqué dans la configuration et produit un rapport de synthèse.

Le rapport permet notamment de consulter :

* le nombre de mesures ;
* la moyenne ;
* le maximum ;
* le minimum ;
* le signalement des doublons.

Le fichier `config.txt` contient les réglages propres à l'environnement de travail et ne doit pas être versionné dans Git.

Pour connaître les différents paramètres disponibles, consulter [les réglages](reglages.md).
