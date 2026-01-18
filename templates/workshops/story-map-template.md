# Story Map Template

## 📋 À propos de ce template

La **Story Map** (User Story Mapping) est un outil créé par Jeff Patton pour visualiser le parcours utilisateur et organiser le backlog produit de manière collaborative. Elle structure les user stories en 2 dimensions : **horizontal (backbone)** = activités utilisateur, **vertical (walking skeleton)** = tâches détaillées par priorité.

**Quand l'utiliser :**
- Planification de roadmap produit
- Priorisation de backlog (MVP, Release 1, Release 2)
- Alignement équipe sur le parcours utilisateur
- Découpage de features complexes en releases

**Durée de création :** 2-4 heures (session collaborative)

---

## 🎯 Structure Story Map (2 Dimensions)

```
BACKBONE (Horizontal) - User Activities
│
├─ [Activity 1] ──── [Activity 2] ──── [Activity 3] ──── [Activity 4]
│       │                  │                  │                  │
│   [Task 1.1]         [Task 2.1]         [Task 3.1]         [Task 4.1]
│   [Task 1.2]         [Task 2.2]         [Task 3.2]         [Task 4.2]
│   [Task 1.3]         [Task 2.3]         [Task 3.3]         [Task 4.3]
│       │                  │                  │                  │
▼   ─────────────────────────────────────────────────────────────
    MVP Line (Walking Skeleton)
    ─────────────────────────────────────────────────────────────
        [Task 1.4]         [Task 2.4]         [Task 3.4]
        [Task 1.5]         [Task 2.5]         [Task 3.5]
    ─────────────────────────────────────────────────────────────
    Release 1
    ─────────────────────────────────────────────────────────────
        [Task 1.6]         [Task 2.6]
    ─────────────────────────────────────────────────────────────
    Release 2
```

---

## 📝 Étape 1 : Définir le Contexte

### Persona/Utilisateur Cible

**Instructions :** Pour qui créons-nous cette story map ? (1-2 personas max)

**Persona principal :**
- Nom : [Ex: Sophie, Designer Freelance]
- Description courte : [Ex: Designer freelance débutante, gère 3-8 projets clients]
- Goal principal : [Ex: Gérer tous ses projets efficacement sans oublier de deadlines]

**Persona secondaire (optionnel) :**
- Nom : [...]
- Description : [...]
- Goal : [...]

---

### User Goal (Big Picture)

**Instructions :** Quel est l'objectif global de l'utilisateur ? (Job to be done principal)

**Format :** "En tant que [persona], je veux [objectif], afin de [bénéfice]"

**Exemple :**
```
En tant que designer freelance, je veux gérer tous mes projets clients de manière organisée et professionnelle, afin de ne jamais manquer de deadline, d'impressionner mes clients, et de gagner du temps pour me concentrer sur le travail créatif.
```

**Votre User Goal :**
```
En tant que [persona],
je veux [objectif],
afin de [bénéfice]
```

---

## 📊 Étape 2 : Créer le Backbone (Activités Utilisateur - Horizontal)

### Instructions

Le **backbone** représente les **grandes activités** de l'utilisateur dans son parcours (étapes macro).

**Caractéristiques d'une bonne activité :**
- ✅ High-level (pas trop détaillé)
- ✅ Centrée utilisateur (verbe d'action du point de vue user)
- ✅ Séquencée de gauche à droite (flow temporel)
- ✅ 5-10 activités maximum (pas plus)

**Exemple (Plateforme gestion projets freelance) :**
1. Découvrir la plateforme
2. S'inscrire et créer un compte
3. Créer son premier projet
4. Gérer les tâches du projet
5. Collaborer avec client/équipe
6. Facturer et suivre les paiements
7. Analyser sa performance

---

### Vos Activités Utilisateur (Backbone)

| # | Activité Utilisateur (Verbe d'action) | Description courte |
|---|---------------------------------------|-------------------|
| 1 | [Ex: Découvrir la plateforme] | [Recherche, landing page, onboarding] |
| 2 | [...] | [...] |
| 3 | [...] | [...] |
| 4 | [...] | [...] |
| 5 | [...] | [...] |
| 6 | [...] | [...] |
| 7 | [...] | [...] |
| 8 | [...] | [...] |

---

## 📊 Étape 3 : Décomposer en Tâches (User Tasks - Vertical)

### Instructions

Pour chaque **activité** (backbone), décomposer en **tâches utilisateur détaillées** (user tasks).

**Caractéristiques d'une bonne task :**
- ✅ Spécifique et actionnable
- ✅ Du point de vue utilisateur (pas technique)
- ✅ Format user story : "En tant que [persona], je veux [action], afin de [bénéfice]"
- ✅ Estimable (effort relatif : S/M/L ou story points)

---

### Activité 1 : [Nom de l'activité 1]

**User Tasks :**

| Task | User Story | Priorité | Effort |
|------|-----------|----------|--------|
| 1.1 | En tant que [persona], je veux [action], afin de [bénéfice] | Must-have | S |
| 1.2 | [...] | Must-have | M |
| 1.3 | [...] | Should-have | S |
| 1.4 | [...] | Could-have | L |

---

### Activité 2 : [Nom de l'activité 2]

**User Tasks :**

| Task | User Story | Priorité | Effort |
|------|-----------|----------|--------|
| 2.1 | [...] | Must-have | M |
| 2.2 | [...] | Should-have | S |
| 2.3 | [...] | Could-have | M |

---

### Activité 3-N : [Répéter pour chaque activité du backbone]

[Copier la structure ci-dessus pour chaque activité]

---

## 📊 Étape 4 : Prioriser et Découper en Releases

### Instructions

Tracer des **lignes horizontales** pour séparer les tasks par priorité/release :

1. **MVP (Walking Skeleton)** : Le parcours utilisateur minimum viable (end-to-end)
2. **Release 1** : Amélioration du MVP (features critiques)
3. **Release 2** : Features nice-to-have (optimisations)
4. **Release 3+** : Future enhancements

**Principe :** Chaque release doit délivrer de la **valeur utilisateur complète** (pas juste des features isolées).

---

### MVP (Walking Skeleton) - Must-Have

**Objectif MVP :** [Décrire en 1-2 phrases ce que l'utilisateur peut accomplir avec le MVP]

**Exemple :** "Avec le MVP, Sophie peut créer un compte, créer son premier projet avec tâches, et voir une vue d'ensemble de ses projets. Elle ne peut pas encore collaborer avec clients ni facturer."

**Tasks incluses dans MVP :**

| Activité | Task # | User Story (résumé) | Effort |
|----------|--------|---------------------|--------|
| [Activité 1] | 1.1 | [Résumé task] | S |
| [Activité 1] | 1.2 | [Résumé task] | M |
| [Activité 2] | 2.1 | [Résumé task] | S |
| [Activité 3] | 3.1 | [Résumé task] | M |
| [Activité 4] | 4.1 | [Résumé task] | S |

**Effort total MVP :** [X story points ou person-weeks]

---

### Release 1 - Should-Have

**Objectif Release 1 :** [Décrire ce que la Release 1 ajoute au MVP]

**Exemple :** "Release 1 ajoute la collaboration avec clients (commentaires, file sharing) et la facturation basique (invoices manuels)."

**Tasks incluses dans Release 1 :**

| Activité | Task # | User Story (résumé) | Effort |
|----------|--------|---------------------|--------|
| [Activité 5] | 5.1 | [Résumé task] | M |
| [Activité 5] | 5.2 | [Résumé task] | S |
| [Activité 6] | 6.1 | [Résumé task] | L |
| [Activité 6] | 6.2 | [Résumé task] | M |

**Effort total Release 1 :** [X story points ou person-weeks]

---

### Release 2 - Could-Have

**Objectif Release 2 :** [Décrire ce que la Release 2 ajoute]

**Tasks incluses dans Release 2 :**

| Activité | Task # | User Story (résumé) | Effort |
|----------|--------|---------------------|--------|
| [...] | [...] | [...] | [...] |

**Effort total Release 2 :** [X story points ou person-weeks]

---

### Release 3+ - Nice-to-Have

**Objectif Release 3+ :** [Features future, pas encore prioritaires]

**Tasks incluses :**
- [Task X]
- [Task Y]
- [Task Z]

---

## 🎯 Frameworks de Priorisation (Optionnel)

### MoSCoW

Classifier chaque task :
- **M** : Must have (MVP)
- **S** : Should have (Release 1)
- **C** : Could have (Release 2)
- **W** : Won't have (backlog futur)

---

### RICE Score

Pour tasks complexes, calculer RICE score :
- **R**each : Combien d'utilisateurs touchés ?
- **I**mpact : Quel impact par utilisateur ? (0.25 - 3)
- **C**onfidence : Quelle confiance ? (0-100%)
- **E**ffort : Combien de person-months ?

**RICE = (R × I × C) / E**

---

### Value vs Effort Matrix

Placer chaque task dans une matrice 2x2 :
- **Quick Wins** : High Value + Low Effort → MVP
- **Strategic Bets** : High Value + High Effort → Release 1
- **Nice to Have** : Low Value + Low Effort → Release 2
- **Money Pit** : Low Value + High Effort → Won't have

---

## 📊 Visualisation Story Map (Exemple Rempli)

### Exemple : Plateforme Gestion Projets Freelance

```
BACKBONE (Horizontal - User Activities)

┌──────────────┬──────────────┬──────────────┬──────────────┬──────────────┐
│  Découvrir   │  S'inscrire  │ Créer projet │Gérer tâches  │  Facturer    │
│  plateforme  │              │              │              │              │
├──────────────┼──────────────┼──────────────┼──────────────┼──────────────┤
│ 1.1 Landing  │ 2.1 Signup   │ 3.1 Créer 1er│ 4.1 Ajouter  │ 5.1 Créer    │
│  page visit  │  (email/pwd) │  projet      │  tâches      │  invoice     │
│              │              │              │              │              │
│ 1.2 Voir     │ 2.2 Onboard  │ 3.2 Nommer & │ 4.2 Marquer  │ 5.2 Envoyer  │
│  features    │  wizard 3-stp│  décrire     │  complété    │  au client   │
├──────────────┼──────────────┼──────────────┼──────────────┼──────────────┤
MVP LINE (Walking Skeleton) ────────────────────────────────────────────────
├──────────────┼──────────────┼──────────────┼──────────────┼──────────────┤
│ 1.3 Pricing  │ 2.3 Invite   │ 3.3 Templates│ 4.3 Sous-    │ 5.3 Track    │
│  page        │  teammates   │  projets     │  tâches      │  paiements   │
│              │              │              │              │              │
│ 1.4 Demo     │              │ 3.4 Dupliquer│ 4.4 Deadlines│ 5.4 Rappels  │
│  video       │              │  projet      │  & alerts    │  auto        │
├──────────────┼──────────────┼──────────────┼──────────────┼──────────────┤
RELEASE 1 ───────────────────────────────────────────────────────────────────
├──────────────┼──────────────┼──────────────┼──────────────┼──────────────┤
│ 1.5 Customer │ 2.4 SSO      │ 3.5 Client   │ 4.5 Comments │ 5.5 Recurring│
│  testimonials│  (Google)    │  portal view │  & notes     │  invoices    │
├──────────────┼──────────────┼──────────────┼──────────────┼──────────────┤
RELEASE 2 ───────────────────────────────────────────────────────────────────
├──────────────┼──────────────┼──────────────┼──────────────┼──────────────┤
│ 1.6 Blog/SEO │              │ 3.6 Budgets  │ 4.6 Time     │ 5.6 Analytics│
│              │              │  & expenses  │  tracking    │  dashboard   │
└──────────────┴──────────────┴──────────────┴──────────────┴──────────────┘
```

---

## ✅ Validation Story Map

### Checklist de qualité

- [ ] **User-centric** : Activités et tasks du point de vue utilisateur (pas technique)
- [ ] **Complète** : Couvre tout le parcours utilisateur end-to-end
- [ ] **Priorisée** : MVP clairement défini, releases séquencées par valeur
- [ ] **Estimée** : Effort relatif défini pour chaque task (S/M/L ou story points)
- [ ] **Validée** : Story map reviewée avec équipe (product, design, dev)
- [ ] **Alignée** : Goals business et user needs reflétés dans la priorisation

---

### Questions de validation

1. **Le MVP est-il viable ?**
   - L'utilisateur peut-il accomplir son job to be done principal avec le MVP ?
   - Le MVP délivre-t-il une valeur complète (pas juste des features isolées) ?

2. **Les releases sont-elles incrémentales ?**
   - Chaque release ajoute-t-elle de la valeur utilisateur significative ?
   - Peut-on lancer chaque release indépendamment ?

3. **Les priorités sont-elles data-driven ?**
   - Basées sur user research, analytics, business goals ?
   - Pas juste sur opinions ou préférences personnelles ?

---

## 📎 Métadonnées

**Persona principal :** [Nom]
**User Goal :** [Résumé 1 phrase]
**Date de création :** [Date]
**Créé par :** [Équipe]
**Dernière mise à jour :** [Date]

**Metrics de succès :**
- [ ] MVP lancé en [X semaines]
- [ ] [X]% utilisateurs complètent le parcours MVP
- [ ] [Métrique business - ex: Retention 30j > 50%]

---

## 🔗 Next Steps

Après avoir créé votre story map :

1. **Convertir en backlog Jira/Linear** (tickets par task)
2. **Estimer l'effort** plus précisément (planning poker avec dev team)
3. **Planifier sprints** (séquencer tasks par sprints 2-week)
4. **Créer prototypes** pour tasks UI-heavy (avant dev)
5. **Définir acceptance criteria** pour chaque task

---

## 📚 Ressources

- **Méthodologie** : Jeff Patton - "User Story Mapping" (livre)
- **Site officiel** : https://www.jpattonassociates.com/user-story-mapping/
- **Tool** : Miro Story Mapping template (gratuit)
- **Vidéo** : Jeff Patton - "Story Mapping 101" (YouTube)

---

**Template version** : 1.0 | **Dernière mise à jour** : Janvier 2026
