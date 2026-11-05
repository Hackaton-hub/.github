# Ajouter une nouvelle compétition

Environ 15 minutes, par un propriétaire de l'organisation. Remplacez `<nom>` par le nom court de la compétition
(minuscules, sans espace, ex. `kiro`).

- [ ] **1. Créer le dépôt depuis le modèle**

  ```bash
  gh repo create Hackaton-hub/<nom> --template Hackaton-hub/modele-competition --private --clone
  ```

  (ou bouton **Use this template** sur [modele-competition](https://github.com/Hackaton-hub/modele-competition)).
  Le dépôt reçoit `.github/CODEOWNERS` (Bambara) et le README à trous.

- [ ] **2. Remplir le README** : remplacez chaque `‹À REMPLIR›` (nom, responsable, dates clés,
  règles spécifiques comme la date limite des tâches). Le lien vers le Project est déjà là.
  Commit direct sur `main` : le dépôt est neuf.

- [ ] **3. Créer l'étiquette de la compétition**

  ```bash
  gh label create <nom> --repo Hackaton-hub/<nom> --color 0e8a16 --description "Compétition <Nom>"
  ```

- [ ] **4. Ajouter l'option au champ Compétition** : dans le [Project](https://github.com/orgs/Hackaton-hub/projects/1), en-tête de colonne
  **Compétition** → *Edit field* → *Add option* → `<Nom>`. Ajoutez aussi la ligne de la compétition
  au tableau du README du Project (⋯ → *Settings* → *README*).

- [ ] **5. Lier le dépôt au Project**

  ```bash
  gh project link 1 --owner Hackaton-hub --repo <nom>
  ```

- [ ] **6. Ajouter le dépôt au workflow auto-add** : Project → ⋯ → *Workflows* → *Auto-add to project*
  → choisir le dépôt `<nom>`, filtre `is:issue,pr is:open`.
  Sur le plan gratuit, le Project n'a qu'**un** workflow auto-add : faites-le pointer sur la compétition en cours.
  Les issues créées avec le formulaire « Nouvelle tâche » arrivent de toute façon dans le Project.

- [ ] **7. Créer le salon Discord** `#<nom>` : *Paramètres du serveur → Intégrations → Webhooks → Nouveau webhook*
  sur ce salon, copiez l'URL. Puis sur GitHub : *Settings du dépôt → Webhooks → Add webhook*
  - Payload URL : l'URL Discord **suivie de `/github`**
  - Content type : `application/json`
  - Événements : *Let me select* → Issues, Pull requests, Pull request reviews

- [ ] **8. Créer les tâches** avec le formulaire « Nouvelle tâche » du dépôt, puis dans le Project :
  Compétition, Échéance, Livrable, Statut, personne assignée.

- [ ] **9. Prévenir l'équipe** sur Discord avec le lien du dépôt et de la vue **Mes tâches**.
