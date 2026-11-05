# Hackaton-hub : comment on travaille

On a remplacé le Google Sheet par GitHub. Toutes les tâches de toutes nos compétitions sont dans **un seul tableau
de suivi**, le Project **[Compétitions](https://github.com/orgs/Hackaton-hub/projects/1)**. Le code et les tâches de chaque compétition vivent dans
**son propre dépôt**.

> **À retenir** : ouvre **[Mes tâches](https://github.com/orgs/Hackaton-hub/projects/1/views/3)**, tiens ton **Statut** à jour, une PR par tâche avec
> `Closes #numéro`, Bambara valide.

---

## 1. Où trouver quoi

| Quoi | Où |
|---|---|
| Le tableau de suivi de toutes les tâches | [Project « Compétitions »](https://github.com/orgs/Hackaton-hub/projects/1) |
| Les règles de l'équipe | [CONTRIBUTING.md](CONTRIBUTING.md) |
| VerifAfrique : code, tâches, règles et dates limites | [Hackaton-hub/verifafrique](https://github.com/Hackaton-hub/verifafrique) |
| Kiro : code, tâches, règles et dates limites | [Hackaton-hub/kiro](https://github.com/Hackaton-hub/kiro) |
| Ajouter une nouvelle compétition | [NOUVELLE_COMPETITION.md](NOUVELLE_COMPETITION.md) |
| Les notifications (nouvelles tâches, PR, validations) | les salons Discord de chaque compétition |

| Rôle | Personne |
|---|---|
| Responsable VerifAfrique | @BHAR-226 |
| Responsable Kiro | @Windyam-Juste-Yannel-BELEMSIGRI |
| Validation de toutes les PR | @BHAR-226 |

---

## 2. Le Project « Compétitions »

Chaque tâche est une **issue** dans le dépôt de sa compétition, et apparaît comme une ligne du Project.

### Les colonnes d'une tâche

| Champ | À quoi il sert | Qui le remplit |
|---|---|---|
| **Status** | À faire · En cours · Bloqué · Terminé | toi, ou automatiquement (voir §3) |
| **Assignees** | qui fait la tâche | à la création |
| **Compétition** | VerifAfrique, Kiro… | à la création |
| **Échéance** | date prévue de fin | **toi**, selon ton programme, sans dépasser la date limite de la compétition |
| **Livrable** | ce qu'il faut rendre | à la création |
| **Rapport** | Non envoyé · Envoyé au responsable · Validé | toi, puis le responsable |

On modifie une case en cliquant dessus, comme dans un tableur.

### Les onglets

| Onglet | Pour quoi faire |
|---|---|
| [Tableau](https://github.com/orgs/Hackaton-hub/projects/1/views/1) | Vue d'ensemble en colonnes par statut. On glisse une carte d'une colonne à l'autre pour changer son statut. |
| [Par compétition](https://github.com/orgs/Hackaton-hub/projects/1/views/2) | Le tableau complet, groupé par compétition et trié par échéance (l'équivalent de l'ancien Google Sheet). |
| [Mes tâches](https://github.com/orgs/Hackaton-hub/projects/1/views/3) | **Uniquement tes tâches.** C'est l'onglet à ouvrir chaque jour. |
| [⚠ Hors délai](https://github.com/orgs/Hackaton-hub/projects/1/views/4) | Les tâches VerifAfrique prévues après le 6 novembre. **Doit rester vide.** |
| [Rapports à valider](https://github.com/orgs/Hackaton-hub/projects/1/views/5) | Les rapports envoyés, en attente de validation par le responsable. |
| [Planning](https://github.com/orgs/Hackaton-hub/projects/1/views/6) | La frise des échéances, pour voir si on tient les dates. |

---

## 3. Ce qui se fait tout seul

| Quand… | …alors |
|---|---|
| une issue est ajoutée au Project | elle passe en **À faire** |
| une PR qui contient `Closes #12` est ouverte | la tâche 12 passe en **En cours** |
| Bambara merge cette PR | l'issue 12 se ferme et la tâche passe en **Terminé** |
| tu mets une tâche en **Terminé** | son issue se ferme |
| une issue est fermée | la tâche passe en **Terminé** |
| une tâche a des sous-tâches | elles sont ajoutées au Project |
| une issue, une PR ou une validation bouge | un message arrive sur Discord |

Les issues de **verifafrique** sont ajoutées au Project automatiquement. Pour les autres dépôts, crée la tâche avec
le formulaire **Nouvelle tâche** (§5) : elle arrive aussi dans le Project.

---

## 4. Le cycle d'une tâche, étape par étape

1. **Je regarde mes tâches** dans [Mes tâches](https://github.com/orgs/Hackaton-hub/projects/1/views/3) et j'ajuste mes **Échéances**.
2. **Je commence** : je passe le Statut à **En cours**.
3. **Si c'est du code**, je travaille sur **ma branche**, à mon prénom, dans le dépôt de la compétition :

   ```bash
   # Première fois dans le dépôt
   git clone https://github.com/Hackaton-hub/verifafrique.git
   cd verifafrique
   git checkout -b ange            # ton prénom
   git push -u origin ange

   # Avant chaque nouvelle tâche : repartir de main à jour
   git checkout ange
   git fetch origin
   git merge origin/main
   ```

4. **J'ouvre une PR par tâche**, avec `Closes #numéro` et Bambara en relecteur :

   ```bash
   gh pr create --base main --head ange --reviewer BHAR-226 --title "[V2] Scraper les données" --body "Closes #2"
   ```

   Ou sur GitHub : *Pull requests → New pull request*. Le modèle de PR se remplit tout seul : coche la checklist.
5. **Je préviens Bambara** sur Discord. Il relit, puis valide et merge. **Je ne merge jamais moi-même.**
   La tâche passe alors en **Terminé** toute seule.
6. **Si ce n'est pas du code** (étude, inscription, rapport…), je passe moi-même le Statut à **Terminé**
   quand le livrable est rendu.
7. **J'envoie mon rapport** (1 à 2 pages) au responsable de la compétition, puis je passe le champ **Rapport**
   à « Envoyé au responsable ». Le responsable le passe à « Validé ».

**Je suis bloqué ?** Statut → **Bloqué**, et j'écris pourquoi en commentaire de l'issue (« j'attends V2 », « besoin
d'aide sur… »).

**Une seule branche par personne** : attends que ta PR soit mergée avant d'attaquer la tâche de code suivante,
sinon les deux tâches se mélangent dans la même PR.

---

## 5. Créer une nouvelle tâche

1. Va dans le dépôt de la compétition → **Issues** → **New issue** → formulaire **Nouvelle tâche**.
2. Remplis le titre, le livrable et les dépendances, puis clique sur **Create**.
3. Dans le Project, remplis **Compétition**, **Échéance**, **Livrable** et la personne assignée.

Les tâches faites par **chaque membre** (comme K1 à K4 pour Kiro) ont une tâche parente « (tous) » et une
sous-tâche par personne. Chacun met à jour **sa** sous-tâche ; la barre de progression de la parente avance
toute seule.

---

## 6. Questions fréquentes

**Je ne vois pas le Project.** Vérifie que tu es connecté à GitHub et que tu as accepté l'invitation à Hackaton-hub.

**Ma tâche n'apparaît pas dans le Project.** Ouvre l'issue → à droite, **Projects** → choisis **Compétitions**.

**J'ai mis Terminé par erreur et l'issue s'est fermée.** Rouvre l'issue (*Reopen issue*), puis remets le bon Statut
dans le Project.

**Où sont les dates limites d'une compétition ?** Dans le README du dépôt de cette compétition.

**On commence une nouvelle compétition.** Suivez [NOUVELLE_COMPETITION.md](NOUVELLE_COMPETITION.md).
