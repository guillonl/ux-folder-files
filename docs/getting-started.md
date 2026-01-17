# Guide de Démarrage - UX Agents Repository

Bienvenue dans le repository d'agents UX/UI spécialisés ! Ce guide vous explique comment utiliser ces agents avec Claude pour améliorer votre pratique du design UX.

---

## 📋 Table des Matières

1. [Qu'est-ce qu'un Agent UX ?](#quest-ce-quun-agent-ux)
2. [Comment Utiliser un Agent avec Claude](#comment-utiliser-un-agent-avec-claude)
3. [Workflows Simples](#workflows-simples)
4. [Workflows Avancés](#workflows-avancés)
5. [Best Practices](#best-practices)
6. [Troubleshooting](#troubleshooting)

---

## Qu'est-ce qu'un Agent UX ?

Un **agent UX** est un fichier `.md` contenant un prompt structuré qui transforme Claude en expert spécialisé pour une tâche UX spécifique.

### Types d'Agents Disponibles

#### 🔍 **Agents d'Analyse** (`/agents/analysis/`)
- **ux-auditor-nielsen.md** : Audit heuristique selon les 10 heuristiques de Nielsen
- **ux-auditor-bastien-scapin.md** : Évaluation ergonomique (18 critères Bastien & Scapin)
- *(À venir)* : accessibility-wcag-checker, design-system-auditor, multi-framework-analyzer

#### 🎯 **Facilitateurs de Workshops** (`/agents/workshops/`)
*(À venir)* : design-thinking-facilitator, design-sprint-conductor, story-mapping-guide, etc.

#### 📊 **Analystes de Données** (`/agents/data-intelligence/`)
*(À venir)* : analytics-interpreter, qualitative-feedback-analyzer, ab-test-analyst, ux-research-scout

#### 📝 **Générateurs de Livrables** (`/agents/deliverables/`)
*(À venir)* : persona-generator, user-journey-mapper, wireframe-descriptor, design-system-documenter

#### 🎛️ **Orchestrateurs** (`/agents/orchestrators/`)
*(À venir)* : ux-workflow-coordinator, conversational-ux-advisor

---

## Comment Utiliser un Agent avec Claude

### Méthode 1 : Copier-Coller (Recommandé pour Débutants)

**Étape 1 : Choisir un Agent**

Naviguez dans `/agents/` et choisissez l'agent correspondant à votre besoin.

Exemple : Vous voulez auditer une interface → `/agents/analysis/ux-auditor-nielsen.md`

**Étape 2 : Copier le Contenu**

Ouvrez le fichier `.md` et copiez **tout le contenu**.

**Étape 3 : Coller dans Claude**

Dans une conversation Claude (Web, Desktop, ou API) :

```
[Collez le contenu complet de l'agent]

---

Maintenant que tu es configuré en tant que [Nom Agent], voici ma demande :

[Votre tâche spécifique]
```

**Exemple concret :**

```
[Contenu complet de ux-auditor-nielsen.md collé ici]

---

Maintenant que tu es configuré en tant que UX Auditor Nielsen, voici ma demande :

Je voudrais un audit de mon interface e-commerce.
Voici le screenshot de la page produit : [image]

Contexte :
- Site e-commerce B2C grand public
- Cible : 25-50 ans, acheteurs occasionnels
- Tâche critique : Ajouter produit au panier et procéder au checkout
- Problème rapporté : Taux d'abandon panier élevé (60%)
```

**Étape 4 : Interagir**

L'agent va poser des questions de clarification si nécessaire, puis exécuter sa tâche selon son process défini.

---

### Méthode 2 : Avec Claude CLI (Pour Utilisateurs Avancés)

Si vous utilisez Claude CLI, vous pouvez utiliser les agents comme prompts système :

```bash
# Exemple avec l'API Claude
cat agents/analysis/ux-auditor-nielsen.md > system_prompt.txt

# Puis dans votre script
claude chat --system-prompt system_prompt.txt
```

---

### Méthode 3 : Projects Claude (Claude.ai)

Sur claude.ai, créez un **Project** et ajoutez le fichier agent dans les "Project Knowledge" :

1. Créer nouveau Project : "UX Audits"
2. Ajouter Knowledge : Upload `ux-auditor-nielsen.md`
3. Dans les conversations du project, Claude aura automatiquement accès à l'agent
4. Demandez simplement : "Agis en tant que UX Auditor Nielsen et analyse cette interface [image]"

---

## Workflows Simples

### Workflow 1 : Audit Heuristique Rapide

**Objectif** : Identifier violations UX d'une interface

**Agent utilisé** : `ux-auditor-nielsen.md`

**Steps** :
1. Copier l'agent Nielsen dans Claude
2. Fournir :
   - Screenshot(s) de l'interface
   - Type d'interface (web app, mobile, etc.)
   - Utilisateurs cibles
   - Tâches principales
3. Recevoir rapport avec :
   - Score global /50
   - Violations par heuristique
   - Priorisation P0/P1/P2/P3
   - Recommandations actionnables

**Temps estimé** : 10-15 minutes

**Exemple de prompt** :
```
[Agent Nielsen collé]

---

Audit de mon dashboard analytics SaaS.
Screenshots : [3 images - vue d'ensemble, détail graphe, settings]

Contexte :
- Dashboard B2B pour data analysts
- Usage quotidien, sessions 2-4h
- Tâches : Créer rapports, analyser tendances, configurer alertes
- Problème : Utilisateurs se plaignent de difficulté à trouver fonctions

Format souhaité : Rapport détaillé pour équipe produit
```

---

### Workflow 2 : Comparaison Multi-Framework

**Objectif** : Audit complet avec perspectives complémentaires (Nielsen + Bastien & Scapin)

**Agents utilisés** :
- `ux-auditor-nielsen.md`
- `ux-auditor-bastien-scapin.md`

**Steps** :
1. **Conversation 1** : Audit Nielsen
   - Copier agent Nielsen
   - Fournir interface + contexte
   - Sauvegarder rapport 1

2. **Conversation 2** : Audit Bastien & Scapin
   - Copier agent Bastien & Scapin
   - Fournir MÊME interface + contexte
   - Demander cross-reference avec Nielsen
   - Sauvegarder rapport 2

3. **Synthèse manuelle** : Consolider les 2 rapports
   - Violations détectées par les 2 → **Critiques**
   - Violations spécifiques B&S → Nuances charge cognitive
   - Violations spécifiques Nielsen → Perspective globale

**Temps estimé** : 30-40 minutes

**Note** : Dans les futures versions, le `multi-framework-analyzer.md` automatisera cette consolidation.

---

### Workflow 3 : Audit Ciblé (Une Seule Heuristique)

**Objectif** : Approfondir une dimension spécifique (ex: Gestion des erreurs)

**Agent utilisé** : `ux-auditor-nielsen.md` ou `ux-auditor-bastien-scapin.md`

**Steps** :
1. Copier agent
2. Dans votre demande, préciser :
   ```
   Focus sur l'heuristique 9 (Error Handling) uniquement.
   Analyse approfondie :
   - Tous les messages d'erreur du parcours checkout
   - Validation de formulaires
   - Gestion erreurs paiement

   Format : Liste détaillée violations + recommandations
   ```

**Temps estimé** : 5-10 minutes

---

## Workflows Avancés

### Workflow A : Audit → Corrections → Validation

**Objectif** : Boucle complète audit → fix → vérification

**Agents utilisés** :
- `ux-auditor-nielsen.md` (x2)
- *(Optionnel futur)* : `wireframe-descriptor.md`

**Steps** :

**Phase 1 : Audit Initial**
1. Audit Nielsen de l'interface actuelle
2. Identifier violations P0 et P1 (top 5-10)
3. Générer rapport Action Items

**Phase 2 : Corrections** (Votre travail de design)
4. Corriger les violations identifiées
5. Créer nouveaux wireframes/mockups

**Phase 3 : Validation**
6. Nouveau audit Nielsen de l'interface corrigée
7. Vérifier que violations P0/P1 sont résolues
8. Rapport comparatif avant/après :
   - Score initial : X/50 → Score final : Y/50
   - Violations P0 : X → 0
   - Améliorations mesurables

**Temps estimé** : 2-3 jours (incluant design)

**Exemple de prompt Phase 3** :
```
[Agent Nielsen]

---

Audit de validation post-corrections.

Interface initiale (auditée il y a 2 jours) avait :
- Score : 32/50
- 5 violations P0 (notamment : pas de feedback sur actions, pas de confirmation suppression, messages erreur cryptiques)

Interface corrigée : [nouveaux screenshots]

Objectif : Vérifier que les P0 sont résolus et calculer nouveau score.
Format : Rapport comparatif avant/après
```

---

### Workflow B : Audit Multi-Pages (Site Complet)

**Objectif** : Auditer un site/app avec multiples pages/écrans

**Agent utilisé** : `ux-auditor-nielsen.md`

**Steps** :

**Option 1 : Audit Global puis Deep Dives**
1. Audit Nielsen avec screenshots des 5-7 écrans principaux
2. Rapport global identifiant patterns systémiques
3. Si violations récurrentes détectées → Deep dive par page

**Option 2 : Audit par User Flow**
4. Définir 3-4 user flows critiques (ex: Inscription, Achat, Support)
5. Pour chaque flow :
   - Audit Nielsen du parcours complet
   - Screenshots de toutes les étapes
   - Rapport spécifique au flow
6. Synthèse finale : Violations cross-flows vs spécifiques

**Temps estimé** : 1-2 heures pour site moyen (10-15 pages)

**Exemple de prompt Option 2** :
```
[Agent Nielsen]

---

Audit du user flow "Inscription nouvel utilisateur" (7 étapes).

Screenshots fournis (7 images) :
1. Landing page avec CTA "S'inscrire"
2. Formulaire inscription (étape 1/3 - infos perso)
3. Formulaire inscription (étape 2/3 - mot de passe)
4. Formulaire inscription (étape 3/3 - préférences)
5. Vérification email (message affiché)
6. Confirmation email (inbox user)
7. Page d'accueil post-inscription

Focus sur :
- Cohérence à travers les étapes (H4)
- Feedback à chaque étape (H1)
- Contrôle utilisateur (H3 - peut-il revenir en arrière ?)
- Gestion erreurs (H9 - validation formulaire)

Format : Rapport par étape + synthèse flow complet
```

---

### Workflow C : Orchestration Multi-Agents (Futur)

*(Ce workflow sera automatisé par `ux-workflow-coordinator.md` dans futures versions)*

**Objectif** : Workflow complet UX avec multiples agents

**Exemple : Discovery → Analyse → Livrables**

**Agents utilisés** :
1. `ux-research-scout.md` : Recherche compétitive
2. `analytics-interpreter.md` : Analyse données existantes
3. `qualitative-feedback-analyzer.md` : Analyse verbatims utilisateurs
4. `ux-auditor-nielsen.md` : Audit heuristique
5. `persona-generator.md` : Création personas basées sur data
6. `user-journey-mapper.md` : Mapping parcours avec pain points

**Steps** :
1. Recherche (agents 1-3) → Insights
2. Audit (agent 4) → Violations
3. Synthèse → Priorisation problèmes
4. Livrables (agents 5-6) → Artefacts pour équipe

**Note** : Aujourd'hui, faire manuellement en conversations séparées. Demain, `ux-workflow-coordinator.md` orchestrera automatiquement.

---

## Best Practices

### ✅ DO

1. **Fournir Contexte Riche**
   - Plus vous donnez d'informations (utilisateurs, tâches, contraintes), meilleur sera l'audit
   - Screenshots multiples > screenshots uniques
   - User flows > pages isolées

2. **Être Spécifique sur l'Output**
   - Préciser format souhaité (Détaillé, Summary, Action Items)
   - Indiquer audience (équipe dev, management, designers)
   - Demander priorisation si besoin sprint planning

3. **Itérer et Approfondir**
   - Commencer par audit global
   - Deep dive sur zones critiques identifiées
   - Poser questions de suivi à l'agent

4. **Combiner Agents**
   - Perspectives multiples (Nielsen + Bastien & Scapin)
   - Spécialisations (Audit global + Accessibilité détaillée)
   - Cross-reference pour renforcer recommandations

5. **Sauvegarder les Rapports**
   - Exporter rapports en markdown
   - Versioning (Audit v1, v2 post-corrections)
   - Partager avec équipe dans outils collaboratifs

---

### ❌ DON'T

1. **Ne Pas Utiliser Sans Contexte**
   - ❌ "Audite cette interface [image]" → Trop vague
   - ✅ "Audite ce dashboard analytics pour data scientists, focus sur efficacité tâches complexes"

2. **Ne Pas Ignorer les Questions de l'Agent**
   - Les agents posent des questions de clarification → Y répondre améliore qualité
   - Si vous ne savez pas → Dites-le, l'agent fera des hypothèses documentées

3. **Ne Pas Mélanger Plusieurs Tâches**
   - ❌ "Fais un audit Nielsen + génère des personas + crée user journey"
   - ✅ Utilisez des conversations séparées ou demandez workflow séquentiel

4. **Ne Pas Négliger la Priorisation**
   - Tous les problèmes ne sont pas égaux
   - Toujours demander scoring P0/P1/P2/P3
   - Focus sur quick wins (impact fort, effort faible)

5. **Ne Pas Oublier la Validation**
   - Après corrections → Re-audit
   - Mesurer amélioration (score avant/après)

---

## Troubleshooting

### Problème : L'agent ne suit pas son process

**Solution** :
- Vérifiez que vous avez collé le contenu COMPLET de l'agent
- Ajoutez après le prompt : "Suis exactement le process défini dans ton rôle"
- Si Claude dévie, rappelez : "Rappel : tu es [Nom Agent], utilise ta méthodologie en 5 étapes"

---

### Problème : Rapport trop générique

**Causes possibles** :
- Contexte insuffisant fourni
- Screenshots peu clairs ou incomplets
- Pas de focus spécifique demandé

**Solution** :
- Fournir plus de détails : utilisateurs, tâches, problèmes connus
- Donner multiples screenshots ou vidéo de user flow
- Demander explicitement : "Sois très spécifique avec exemples concrets et localisations précises"

---

### Problème : Rapport trop long / trop court

**Solution pour trop long** :
- Demander format "Executive Summary" plutôt que "Rapport Détaillé"
- Préciser : "Top 10 violations uniquement"
- Focus sur une heuristique/dimension spécifique

**Solution pour trop court** :
- Demander format "Rapport Détaillé"
- Préciser : "Pour chaque violation, fournis exemple concret, impact utilisateur, recommandation actionnable"
- Demander deep dive : "Approfondis les violations P0 avec analyse détaillée"

---

### Problème : Je ne sais pas quel agent utiliser

**Solution** :
Utilisez cette decision tree :

```
Quel est votre objectif ?

├─ Analyser une interface existante
│  ├─ Audit rapide, perspective globale → ux-auditor-nielsen.md
│  ├─ Audit détaillé, charge cognitive → ux-auditor-bastien-scapin.md
│  ├─ Accessibilité spécifiquement → (futur) accessibility-wcag-checker.md
│  └─ Design system consistency → (futur) design-system-auditor.md
│
├─ Faciliter un workshop
│  ├─ Design Thinking → (futur) design-thinking-facilitator.md
│  ├─ Design Sprint → (futur) design-sprint-conductor.md
│  └─ Story Mapping → (futur) story-mapping-guide.md
│
├─ Analyser des données
│  ├─ Analytics (GA, mixpanel) → (futur) analytics-interpreter.md
│  ├─ Feedback qualitatif → (futur) qualitative-feedback-analyzer.md
│  └─ A/B tests → (futur) ab-test-analyst.md
│
├─ Créer des livrables
│  ├─ Personas → (futur) persona-generator.md
│  ├─ User Journeys → (futur) user-journey-mapper.md
│  └─ Documentation design system → (futur) design-system-documenter.md
│
└─ Pas sûr / workflow complexe
   └─ (futur) conversational-ux-advisor.md → Guidera vers bon agent
```

---

### Problème : Résultats incohérents entre 2 audits

**Causes possibles** :
- Contexte différent fourni entre les 2 audits
- Screenshots différents (versions interface différentes)
- Agents différents (Nielsen vs Bastien & Scapin ont focus différents)

**Solution** :
- Pour comparaison avant/après : Utiliser MÊME agent, MÊME format, MÊME niveau de détail
- Documenter clairement ce qui a changé entre les 2 versions
- Demander explicitement rapport comparatif

---

## Prochaines Étapes

### Niveau Débutant
1. ✅ Lisez ce guide entièrement
2. Testez un audit simple avec `ux-auditor-nielsen.md` sur une interface que vous connaissez
3. Expérimentez les 3 formats de rapport (Détaillé, Summary, Action Items)

### Niveau Intermédiaire
4. Essayez audit multi-framework (Nielsen + Bastien & Scapin)
5. Faites un audit → corrections → validation
6. Explorez les frameworks de référence (`/frameworks/`) pour comprendre méthodologies

### Niveau Avancé
7. Créez workflows multi-agents personnalisés
8. Contribuez de nouveaux agents (voir `/README.md` - section Contribution)
9. Automatisez avec API Claude et scripts

---

## Ressources Complémentaires

### Documentation du Repository
- **README.md** : Vue d'ensemble du projet, navigation
- **frameworks/** : Références méthodologiques complètes (Nielsen, Bastien & Scapin, WCAG...)
- **agents/** : Tous les agents disponibles par catégorie

### Références Externes
- **Nielsen Norman Group** : https://www.nngroup.com
- **INRIA (Bastien & Scapin)** : https://www.lamsade.dauphine.fr/~manouvri/IHM/Bastien-Scapin.pdf
- **WCAG Guidelines** : https://www.w3.org/WAI/WCAG21/quickref/

### Support
- **Issues GitHub** : [À compléter avec lien repo]
- **Contributions** : Voir README.md - Guidelines de contribution
- **Questions** : [À compléter avec canal support]

---

## Changelog

- **v1.0 (2026-01)** : Version initiale
  - Agents d'analyse : Nielsen, Bastien & Scapin
  - Frameworks : Nielsen 10 heuristiques, Bastien & Scapin 18 critères
  - Documentation : Getting Started

- **v1.1 (À venir)** :
  - Workshop facilitators
  - Data intelligence agents
  - Multi-framework analyzer

---

**Bon audit ! 🚀**

*Ce guide sera mis à jour au fur et à mesure de l'ajout de nouveaux agents et workflows.*
