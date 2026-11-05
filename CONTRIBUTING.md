# Règles de travail de l'équipe

Ces règles valent pour **toutes** les compétitions de l'organisation Hackaton-hub.
Les règles propres à une compétition (responsable, dates limites, livrables) sont dans le
**README du dépôt de cette compétition**.

Toutes les tâches sont suivies dans le Project d'organisation **[Compétitions](https://github.com/orgs/Hackaton-hub/projects/1)**.

| Rôle | Personne |
|---|---|
| Responsable d'une compétition | indiqué dans le README du dépôt de la compétition |
| Validation des PR | **le responsable de la compétition** du dépôt |
| Rapports de fin de tâche | **le responsable de la compétition** du dépôt |

## 1. Échéances

Chacun ajuste l'échéance (champ **Échéance** du Project) de ses tâches selon son programme.
Les dates limites propres à chaque compétition sont dans le README de son dépôt : aucune échéance ne doit les dépasser.

## 2. Rapport de fin de tâche

À la fin de chaque tâche, rédigez un rapport de **1 à 2 pages** et envoyez-le au **responsable de la compétition**
(indiqué dans le README du dépôt).

Passez ensuite le champ **Rapport** à « Envoyé au responsable ». Le responsable rassemble les rapports,
s'assure que les tâches sont faites et passe le champ à « Validé ».

## 3. Une PR par tâche

Chaque tâche de code donne **une** pull request. Dans la description, écrivez `Closes #<numéro de l'issue>` :
l'issue se ferme toute seule au merge et la tâche passe en « Terminé ».

## 4. Une seule branche par personne

Dans chaque dépôt, chacun programme sur **sa** branche, nommée par son prénom : `ange`, `bambara`, `windyam`, `faissal`.

```bash
# Première fois dans un dépôt
git checkout -b ange
git push -u origin ange

# Avant chaque nouvelle tâche : repartir de main à jour
git checkout ange
git fetch origin
git merge origin/main

# Ouvrir la PR de la tâche, avec le responsable de la compétition en relecteur
# (exemple VerifAfrique, dont le responsable est @BHAR-226)
gh pr create --base main --head ange --reviewer BHAR-226 --title "[V2] Scraper les données" --body "Closes #12"
```

Comme il n'y a qu'une branche par personne, **attendez que votre PR soit validée et mergée avant d'enchaîner
sur la tâche de code suivante**. Sinon, les deux tâches se mélangent dans la même PR.

## 5. Validation des PR

Chaque PR est validée par **le responsable de la compétition** du dépôt (indiqué dans son README).
Quand votre PR est prête, demandez-lui la relecture (option `--reviewer` ou bouton *Reviewers*)
et prévenez-le sur Discord. Ne mergez pas sans sa validation.

## 6. Statut des tâches

Gardez le **Statut** à jour dans le Project :

| Statut | Quand |
|---|---|
| À faire | Pas commencée |
| En cours | Vous travaillez dessus |
| Bloqué | Vous attendez une autre tâche ou de l'aide : expliquez pourquoi en commentaire de l'issue |
| Terminé | Livrable rendu, PR validée, rapport envoyé |

## Nouvelle compétition

Voir [NOUVELLE_COMPETITION.md](https://github.com/Hackaton-hub/.github/blob/main/NOUVELLE_COMPETITION.md).
