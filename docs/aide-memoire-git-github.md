# Aide-mémoire Git et GitHub — module Travail collaboratif & documentation technique

Bachelor 2 - 2026-2027 · Dépôt d'équipe : `releve-cli-nom1-nom2`. Les parties entre chevrons `<…>` sont à remplacer.

## 1. Démarrer

| Geste | Où | Comment |
|---|---|---|
| Créer le dépôt d'équipe | Page du dépôt-modèle | **Use this template → Create a new repository**, nom `releve-cli-nom1-nom2`, *Public* |
| Inviter son binôme | Settings → Collaborators | *Add people*, puis le binôme accepte l'invitation reçue par courriel |
| Récupérer le dépôt sur son poste | terminal | `git clone https://github.com/<compte>/releve-cli-nom1-nom2.git` puis `cd releve-cli-nom1-nom2` |
| Vérifier son identité Git | terminal | `git config --global user.name "Prénom Nom"` · `git config --global user.email "prenom.nom@ynov.com"` |

## 2. Le cycle d'une contribution (toujours dans cet ordre)

```bash
git switch main && git pull                       # 1. partir d'un main à jour
git switch -c fix/<sujet-en-minuscules>           # 2. une branche par sujet : fix/, docs/, feat/, chore/
# ... modifier les fichiers ...
git status                                        # 3. voir ce qui a changé
git add <fichier>                                 # 4. choisir ce qui entre dans l'enregistrement
git commit -m "fix: <description à l'impératif>"  # 5. enregistrer, message préfixé
git push -u origin fix/<sujet>                    # 6. publier la branche
```

> Résultat attendu après le `push` : la plateforme propose **Compare & pull request** sur la branche publiée.

Préfixes de message : `feat:` nouveauté · `fix:` correction · `docs:` documentation · `chore:` entretien (Conventional Commits).

## 3. Issue, pull request, revue — sur la plateforme

| Objet | Où | Ce qu'il contient | À retenir |
|---|---|---|---|
| **Issue** | onglet *Issues* → *New issue* | titre = le manque · **Contexte** · **Comportement attendu / observé** · **Étapes pour reproduire** | signale, ne corrige pas ; obtient un numéro `#n` |
| **Pull request** | bouton *Compare & pull request* | titre = la correction · **Contexte** (avec `Closes #n`) · **Changements** · **Impact** | le modèle du dépôt pré-remplit les trois titres |
| **Lien issue ↔ PR** | description de la PR | `Closes #1`, `Fixes #1` ou `Resolves #1` | ferme l'issue à la fusion ; `voir #1` lie sans fermer |
| **Revue** | onglet *Files changed* de la PR | commentaires ancrés à une ligne (icône **+**), puis *Review changes* | un seul statut pour toute la revue : **Approve** / **Request changes** / **Comment** |
| **Fusion** | bas de la PR | *Merge pull request* → *Confirm* | l'auteur ne peut pas approuver sa propre PR ; la branche peut être supprimée après |

Après une fusion, sur chaque poste : `git switch main && git pull`.

## 4. Lire l'état du dépôt

```bash
git log --oneline --graph --all     # l'historique, toutes branches
git branch -a                       # branches locales et distantes
git ls-files                        # les fichiers réellement suivis (config.txt ne doit PAS y être)
git diff                            # ce qui a changé et n'est pas encore enregistré
git show <hash>                     # le détail d'un enregistrement
```

## 5. Quand ça bloque

| Message | Cause | Que faire |
|---|---|---|
| `! [rejected] main -> main (fetch first)` | le dépôt distant a des enregistrements que le poste n'a pas | `git pull`, rejouer sa fusion si besoin, puis `git push` ; **jamais** `--force` sur `main` |
| `fatal: not a git repository` | commande lancée hors du dossier du dépôt | `cd releve-cli-nom1-nom2` |
| `Permission denied` / `403` au `push` | pas collaborateur du dépôt, ou mauvais compte | demander l'invitation ; vérifier `git remote -v` |
| `CONFLICT (content)` à la fusion | deux modifications sur les mêmes lignes | ouvrir le fichier, choisir entre les marqueurs `<<<<<<<` `=======` `>>>>>>>`, `git add`, `git commit` |
| `Please tell me who you are` | identité Git non configurée | les deux commandes `git config --global` du § 1 |

Message de blocage à l'équipe, en quatre temps : **Contexte** (ce que je faisais) · **Tenté** (ce que j'ai déjà vérifié) · **Bloque** (le message d'erreur copié tel quel) · **Besoin** (ce qu'il me faut pour continuer).

## 6. Ce qui ne se versionne jamais

`config.txt`, `.env`, tout fichier contenant un identifiant, un mot de passe ou un jeton réels. Le dépôt contient `config.example.txt` (valeurs fictives) et `.gitignore` (qui exclut `config.txt`). Une valeur réelle publiée une fois, même supprimée ensuite, reste dans l'historique : elle est compromise et doit être renouvelée.

## 7. Où ranger quoi

| Nature de l'information | Emplacement | Exemples |
|---|---|---|
| Ce qui se relit, se versionne et se date avec le projet | **dépôt Git** | README, `docs/`, fiches de décision, configuration d'exemple |
| Problèmes, besoins, propositions de changement | **Issues et PR** | issue #1, PR qui la corrige, commentaires de revue |
| Collectif et non technique | **Wiki** | comptes rendus de réunion, calendrier, accueil des nouveaux |
| Coordination immédiate (éphémère) | **chat** | « je prends l'issue #1 », « quelqu'un est dispo pour relire ? » |
