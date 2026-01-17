# Les 10 Heuristiques d'Utilisabilité de Jakob Nielsen

## Référence Framework

Ce document présente les 10 heuristiques d'utilisabilité de Jakob Nielsen (Nielsen Norman Group), reconnues comme standard de l'industrie pour l'évaluation heuristique des interfaces utilisateur.

---

## 1. Visibility of System Status (Visibilité du statut du système)

### Principe
Le système doit toujours tenir les utilisateurs informés de ce qui se passe, à travers des retours appropriés dans un délai raisonnable.

### Critères de vérification
- **Feedback immédiat** : Chaque action utilisateur génère une réponse visible (< 0,1s pour interactions directes, < 1s pour traitements)
- **États de chargement** : Spinners, progress bars, skeleton screens pour opérations longues
- **Confirmation d'actions** : Messages de succès/erreur après soumissions
- **Indicateurs de localisation** : Breadcrumbs, navigation active, fil d'Ariane
- **États du système** : Online/offline, synchronisation, sauvegarde auto

### Exemples de violations
- Bouton cliqué sans feedback visuel
- Upload sans progress bar
- Formulaire soumis sans message de confirmation
- Navigation sans indication de page active

### Bonnes pratiques
- Toast notifications pour confirmations non-bloquantes
- Progress indicators avec pourcentage pour opérations longues
- Micro-interactions pour feedback tactile (hover, pressed states)
- Désactivation visuelle de boutons pendant traitement

---

## 2. Match Between System and the Real World (Correspondance système-monde réel)

### Principe
Le système doit parler le langage des utilisateurs, avec des mots, phrases et concepts familiers plutôt que jargon technique. Suivre les conventions du monde réel.

### Critères de vérification
- **Langage naturel** : Terminologie métier plutôt que technique
- **Métaphores familières** : Icônes et concepts connus (corbeille, dossiers, panier)
- **Ordre logique** : Information présentée dans un ordre naturel pour l'utilisateur
- **Unités compréhensibles** : Dates, devises, mesures selon conventions locales
- **Ton approprié** : Formel vs informel selon contexte et audience

### Exemples de violations
- "Erreur 404" au lieu de "Page introuvable"
- Jargon technique dans messages utilisateur ("Exception null pointer")
- Icônes abstraites sans correspondance réelle
- Format de date incohérent avec locale (MM/DD/YYYY en France)

### Bonnes pratiques
- Utiliser vocabulaire du domaine métier
- Icônes universelles (enveloppe = email, maison = accueil)
- Dates relatives ("il y a 2 heures" vs timestamp)
- Messages d'erreur en langage clair avec solution

---

## 3. User Control and Freedom (Contrôle et liberté de l'utilisateur)

### Principe
Les utilisateurs font souvent des erreurs. Ils ont besoin d'une "sortie de secours" claire pour quitter un état non désiré sans passer par un dialogue étendu.

### Critères de vérification
- **Undo/Redo** : Annulation et rétablissement d'actions
- **Annulation facile** : Boutons "Annuler" ou "Retour" visibles
- **Sortie claire** : Fermeture de modals, wizards, flux (× ou "Fermer")
- **Navigation libre** : Pas de blocages forcés, skip possible
- **Sauvegarde états** : Drafts, sessions persistées

### Exemples de violations
- Modal sans bouton de fermeture
- Wizard multi-étapes sans possibilité de retour
- Suppression sans possibilité d'annulation
- Formulaire perdu si navigation arrière

### Bonnes pratiques
- Ctrl+Z universel pour annulation
- Corbeille avec récupération (30 jours)
- "Êtes-vous sûr ?" pour actions destructives
- Sauvegarde automatique de brouillons
- Breadcrumbs cliquables pour navigation rapide

---

## 4. Consistency and Standards (Cohérence et standards)

### Principe
Les utilisateurs ne doivent pas se demander si différents mots, situations ou actions signifient la même chose. Suivre les conventions de la plateforme et de l'industrie.

### Critères de vérification
- **Cohérence interne** : Terminologie, UI patterns, interactions identiques partout
- **Standards plateforme** : Respecter iOS HIG, Material Design, etc.
- **Conventions industrie** : Comportements attendus (logo en haut à gauche = accueil)
- **Design tokens** : Colors, typography, spacing uniformes
- **Patterns réutilisés** : Composants identiques pour fonctions similaires

### Exemples de violations
- "Enregistrer" sur une page, "Sauvegarder" sur une autre
- Bouton primaire bleu parfois, vert ailleurs
- Icône × ferme modal ici, annule action là
- Formulaires avec layouts différents sans raison

### Bonnes pratiques
- Design system avec composants documentés
- Style guide partagé (terminologie, tone of voice)
- Respect des patterns OS (swipe to delete sur iOS)
- Audit régulier de cohérence

---

## 5. Error Prevention (Prévention des erreurs)

### Principe
Mieux vaut prévenir les erreurs que de fournir de bons messages d'erreur. Éliminer les conditions sujettes aux erreurs ou vérifier et présenter une option de confirmation.

### Critères de vérification
- **Contraintes proactives** : Désactivation d'options invalides
- **Validation temps réel** : Feedback immédiat sur input invalide
- **Confirmations** : Double-vérification pour actions critiques/irréversibles
- **Defaults intelligents** : Pré-remplissage avec valeurs probables
- **Guidage visuel** : Formats attendus indiqués, exemples fournis

### Exemples de violations
- Formulaire validé seulement à la soumission
- Suppression en un clic sans confirmation
- Champs de date en texte libre sans format
- Bouton "Supprimer" à côté de "Modifier" sans protection

### Bonnes pratiques
- Validation inline avec messages constructifs
- Confirmation modale pour suppressions : "Supprimer [nom item] ?"
- Input masking (formats téléphone, carte bancaire)
- Disabled states pour actions non disponibles
- Suggestions autocomplete pour éviter fautes

---

## 6. Recognition Rather Than Recall (Reconnaissance plutôt que mémorisation)

### Principe
Minimiser la charge cognitive en rendant objets, actions et options visibles. L'utilisateur ne devrait pas avoir à se souvenir d'informations d'une partie du dialogue à une autre.

### Critères de vérification
- **Visibilité des options** : Actions disponibles clairement affichées
- **Historique accessible** : Commandes récentes, items consultés
- **Auto-complétion** : Suggestions basées sur contexte
- **Tooltips** : Aide contextuelle sur hover
- **Récapitulatifs** : Synthèse avant validation (checkout, formulaires multi-étapes)

### Exemples de violations
- Interface ligne de commande sans aide
- Formulaire multi-pages sans récapitulatif des infos saisies
- Actions cachées sans affordance
- Syntaxe de recherche complexe à mémoriser

### Bonnes pratiques
- Menus déroulants au lieu de saisie libre
- Historique de recherche
- Récapitulatif avant soumission finale
- Icônes + labels (double encoding)
- Recently viewed / frequently used

---

## 7. Flexibility and Efficiency of Use (Flexibilité et efficacité d'utilisation)

### Principe
Les raccourcis — invisibles aux novices — accélèrent les experts. Le système doit convenir aux utilisateurs novices et expérimentés.

### Critères de vérification
- **Raccourcis clavier** : Shortcuts pour actions fréquentes
- **Personnalisation** : Dashboards, favoris, préférences
- **Modes accélérés** : Bulk actions, batch operations
- **Apprentissage progressif** : Découverte graduelle de fonctionnalités avancées
- **Mémorisation d'état** : Filtres sauvegardés, vues personnalisées

### Exemples de violations
- Pas de raccourcis clavier
- Obligation de traiter items un par un (pas de sélection multiple)
- Interface identique pour novice et power user
- Pas de sauvegarde de préférences

### Bonnes pratiques
- Ctrl+S pour sauvegarder, Ctrl+F pour rechercher
- Actions groupées (sélectionner plusieurs emails → archiver)
- Templates personnalisables
- Quick actions (right-click menus)
- Keyboard navigation complète

---

## 8. Aesthetic and Minimalist Design (Design esthétique et minimaliste)

### Principe
Les dialogues ne doivent pas contenir d'information irrelevante ou rarement nécessaire. Chaque unité d'information supplémentaire diminue la visibilité relative des autres.

### Critères de vérification
- **Hiérarchie visuelle** : Information importante mise en avant
- **Progressive disclosure** : Détails avancés cachés par défaut
- **Densité information** : Ni trop chargé, ni trop vide
- **Whitespace** : Respiration visuelle, groupement logique
- **Suppression superflu** : Chaque élément a une fonction claire

### Exemples de violations
- Dashboard surchargé de widgets inutiles
- Texte d'aide omniprésent masquant contenu
- Décorations graphiques sans fonction
- Tous les paramètres avancés visibles d'emblée

### Bonnes pratiques
- Afficher 20% des fonctionnalités utilisées 80% du temps
- Accordions/tabs pour contenu secondaire
- "Advanced options" repliées par défaut
- Iconographie intentionnelle (chaque icône = action claire)
- Focus sur tâche principale par page

---

## 9. Help Users Recognize, Diagnose, and Recover from Errors (Aide à reconnaître, diagnostiquer et récupérer des erreurs)

### Principe
Les messages d'erreur doivent être exprimés en langage clair (pas de codes), indiquer précisément le problème et suggérer constructivement une solution.

### Critères de vérification
- **Langage clair** : Pas de codes techniques (ou expliqués)
- **Localisation précise** : Quel champ/élément pose problème
- **Explication** : Pourquoi c'est une erreur
- **Solution constructive** : Comment corriger
- **Ton approprié** : Pas de blâme, empathique

### Exemples de violations
- "Error 500" sans contexte
- "Invalid input" sans dire quel champ
- Message d'erreur en rouge sans explication
- Blâmer l'utilisateur : "Vous avez fait une erreur"

### Bonnes pratiques
- "Le mot de passe doit contenir 8 caractères minimum, 1 majuscule et 1 chiffre"
- Surligner le champ en erreur
- Icône d'erreur + message clair + lien vers aide
- Ton : "Ce format d'email n'est pas reconnu. Vérifiez qu'il contient @"
- Suggestions : "Vouliez-vous dire [suggestion] ?"

---

## 10. Help and Documentation (Aide et documentation)

### Principe
Même si mieux vaut un système utilisable sans documentation, il peut être nécessaire de fournir une aide. Elle doit être facile à chercher, centrée sur la tâche utilisateur, avec étapes concrètes.

### Critères de vérification
- **Accessibilité** : Aide contextuelle accessible depuis n'importe où
- **Recherchable** : Search bar dans documentation
- **Orientée tâches** : "Comment faire X" plutôt que specs techniques
- **Concise** : Pas de jargon, étapes claires
- **Exemples** : Screenshots, vidéos, cas d'usage

### Exemples de violations
- Lien "Aide" menant à PDF de 200 pages
- Documentation technique pour utilisateurs finaux
- Aide générique sans contexte de la page actuelle
- Pas de fonction de recherche dans l'aide

### Bonnes pratiques
- "?" contextuel affichant aide pour feature actuelle
- Tooltips sur hover pour fonctions complexes
- Base de connaissances avec articles par tâche
- Vidéos tutoriels courts (< 2 min)
- Chatbot ou support in-app
- Onboarding interactif pour nouveaux utilisateurs

---

## Utilisation de ce Framework

### Pour Audit Heuristique
1. Évaluer chaque heuristique sur échelle 1-5 :
   - **1** : Aucune violation
   - **2** : Violations mineures, impact faible
   - **3** : Violations modérées, impact moyen
   - **4** : Violations importantes, impact fort
   - **5** : Violations critiques, blocage utilisateur

2. Pour chaque violation :
   - Localiser précisément (screenshot, URL, user flow)
   - Décrire le problème
   - Évaluer impact et fréquence
   - Recommander solution concrète

3. Prioriser corrections :
   - **P0 (Critique)** : Score 5, impact fort, fréquence haute
   - **P1 (Haute)** : Score 4, impact moyen-fort
   - **P2 (Moyenne)** : Score 3, impact modéré
   - **P3 (Basse)** : Score 1-2, impact faible

### Sources
- Nielsen Norman Group : https://www.nngroup.com/articles/ten-usability-heuristics/
- Jakob Nielsen, "Usability Engineering" (1993)
- Mises à jour et refinements (1994, 2005, 2020)
