# Liste de contrôle — relecture d'une documentation

À appliquer à la documentation d'un autre binôme, puis à la vôtre avant remise.
Chaque ligne donne lieu soit à un constat conforme, soit à une remarque écrite
déposée sur la demande de fusion, rattachée à la ligne du document concernée.

| # | Ce qui est vérifié | Question posée au document | Constat attendu |
|---|---|---|---|
| 1 | Présentation | Une phrase dit-elle ce que fait le projet et à qui il s'adresse ? | Présente en tête de fichier, compréhensible sans contexte |
| 2 | Prérequis | Ce qu'il faut avoir avant de commencer est-il écrit ? | Liste explicite, aucun prérequis supposé |
| 3 | Procédure | Les commandes sont-elles copiables, une par ligne, dans un bloc ? | Blocs présents et exécutables tels quels |
| 4 | Résultat | La procédure dit-elle ce que l'on doit obtenir à la fin ? | Résultat attendu écrit, formulé de façon qu'un lecteur puisse le constater seul |
| 5 | Structure | Les titres respectent-ils une hiérarchie sans saut de niveau ? | Un seul titre de niveau 1, sous-titres cohérents |
| 6 | Implicite | Le texte contient-il « il suffit de », « simplement » ou « évidemment » ? | Aucune de ces formules, ou étape explicitée |
| 7 | Sigles | Chaque abréviation est-elle développée à sa première occurrence ? | Toutes développées |
| 8 | Secrets | Une valeur réelle de configuration figure-t-elle dans le dépôt ? | Aucune valeur réelle, uniquement des exemples |
| 9 | Liens | Les renvois vers les autres documents fonctionnent-ils ? | Chemins relatifs valides depuis la racine (exception : `docs/architecture.md`, cité en texte, séance 3) |
| 10 | Rendu | Le document s'affiche-t-il correctement sur la plateforme ? | Tableaux, listes et blocs rendus comme attendu |

## Comment formuler une remarque

- Une question ou une proposition, jamais un jugement : « la procédure ne dit pas
  ce que l'on doit obtenir à la fin, que faut-il constater ? ».
- Rattachée à une ligne précise du document, pas déposée en commentaire général.
- Accompagnée du numéro de la ligne de cette liste à laquelle elle se rapporte.
