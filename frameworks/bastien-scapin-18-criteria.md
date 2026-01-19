# Les 18 Critères Ergonomiques de Bastien & Scapin

## Référence Framework

Ce document présente les 18 critères ergonomiques de Bastien et Scapin (INRIA, 1993), framework de référence francophone pour l'évaluation ergonomique des interfaces homme-machine.

Structure : **6 dimensions principales** contenant **18 critères** au total, avec sous-critères détaillés.

---

## DIMENSION 1 : GUIDAGE

Le guidage consiste à guider l'utilisateur lors de ses interactions avec le système (messages, alarmes, labels, etc.).

### 1.1 Incitation (Prompting)

#### Principe
L'interface doit inciter l'utilisateur à effectuer des actions spécifiques en fournissant des indices sur les actions attendues et leur localisation.

#### Critères de vérification
- **Labels explicites** : Titres de fenêtres, étiquettes de champs clairs
- **Indices visuels** : Affordances, call-to-action visibles
- **Messages incitatifs** : "Cliquez ici pour...", placeholders informatifs
- **Statut de champs** : Required, optional, format attendu

#### Exemples de violations
- Bouton sans label (juste une icône ambiguë)
- Champ de formulaire sans indication du format attendu
- Absence d'indication visuelle sur élément interactif

#### Bonnes pratiques
- Asterisk (*) pour champs obligatoires
- Placeholders avec exemples : "ex: jean.dupont@email.com"
- Boutons avec verbes d'action : "Enregistrer", "Télécharger"
- Hover states indiquant interactivité

---

### 1.2 Groupement/Distinction par la Localisation

#### Principe
Regrouper visuellement les items liés et séparer les groupes distincts par leur localisation à l'écran.

#### Critères de vérification
- **Proximité** : Éléments liés proches spatialement
- **Séparation** : Whitespace entre groupes distincts
- **Sections** : Délimitation claire (borders, backgrounds)
- **Ordre logique** : Groupement par fonction/thématique

#### Exemples de violations
- Formulaire sans sections visuelles
- Navigation mixée avec contenu principal sans séparation
- Boutons d'action dispersés sans logique

#### Bonnes pratiques
- Cards pour grouper informations liées
- Dividers entre sections
- Fieldsets dans formulaires
- Spatial consistency (même type d'info toujours même zone)

---

### 1.3 Groupement/Distinction par le Format

#### Principe
Utiliser des attributs visuels (couleur, police, taille, style) pour distinguer catégories d'informations.

#### Critères de vérification
- **Hiérarchie typographique** : H1, H2, H3 visuellement distincts
- **Couleur sémantique** : Rouge = erreur, vert = succès, bleu = info
- **Poids de police** : Bold pour emphase, regular pour corps
- **Taille** : Éléments importants plus grands

#### Exemples de violations
- Tout le texte même taille et style
- Couleurs aléatoires sans signification
- Manque de hiérarchie visuelle

#### Bonnes pratiques
- Scale typographique cohérente (8px baseline)
- Couleurs système : success, warning, error, info
- Icons + couleur pour double encoding
- Bold pour labels, regular pour valeurs

---

### 1.4 Feedback Immédiat

#### Principe
Le système doit répondre immédiatement à toute action utilisateur avec un feedback approprié.

#### Critères de vérification
- **Rapidité** : < 100ms pour interactions directes
- **Visibilité** : Changement d'état visible (hover, active, disabled)
- **Confirmation** : Messages après actions importantes
- **Progress indicators** : Pour opérations longues

#### Exemples de violations
- Bouton cliqué sans réaction visuelle
- Formulaire soumis sans confirmation
- Chargement long sans indicator
- Sauvegarde silencieuse sans feedback

#### Bonnes pratiques
- Pressed states sur tous boutons
- Toast notifications pour confirmations
- Spinners/progress bars pour loading
- Validation inline temps réel
- Micro-animations (checkmark après succès)

---

### 1.5 Lisibilité

#### Principe
Les caractéristiques lexicales (police, taille, contraste) doivent faciliter la lecture.

#### Critères de vérification
- **Contraste** : Ratio 4.5:1 minimum (WCAG AA)
- **Taille police** : Minimum 16px pour corps de texte
- **Longueur ligne** : 50-75 caractères optimal
- **Espacement** : Line-height 1.5 minimum
- **Police** : Sans-serif pour écrans, lisible

#### Exemples de violations
- Texte gris clair sur fond blanc
- Police 11px pour contenu principal
- Lignes de 120 caractères sans césure
- Line-height 1.0 (texte tassé)

#### Bonnes pratiques
- Contraste AAA (7:1) pour texte important
- 16-18px minimum corps de texte
- Max-width 65ch pour paragraphes
- Line-height 1.5-1.8
- Fonts web optimisées (Inter, Roboto, System UI)

---

## DIMENSION 2 : CHARGE DE TRAVAIL

Réduire la charge cognitive et perceptive de l'utilisateur.

### 2.1 Brièveté - Concision

#### Principe
Limiter la quantité d'informations à lire, saisir, mémoriser pour réduire la charge de travail.

#### Critères de vérification
- **Textes courts** : Messages concis, sans verbiage
- **Inputs minimaux** : Pré-remplissage, defaults intelligents
- **Labels courts** : 1-3 mots maximum
- **Menus courts** : Éviter listes > 7 items sans catégorisation

#### Exemples de violations
- Messages d'erreur de 3 paragraphes
- Formulaires demandant infos disponibles ailleurs
- Labels verbeux : "Veuillez entrer votre adresse email ici"
- Menus déroulants avec 50 options non groupées

#### Bonnes pratiques
- Microcopy : "Email" au lieu de "Adresse email"
- Autocomplete pour formulaires
- Defaults basés sur contexte utilisateur
- Chunking : grouper listes longues par catégories

---

### 2.2 Brièveté - Actions Minimales

#### Principe
Limiter le nombre d'actions nécessaires pour accomplir une tâche.

#### Critères de vérification
- **Raccourcis** : Chemins rapides pour tâches fréquentes
- **Actions groupées** : Bulk operations
- **Éviter redondance** : Pas de double confirmation inutile
- **Smart defaults** : Sélection automatique d'options probables

#### Exemples de violations
- 5 clics pour action simple
- Obligation de saisir infos déjà connues du système
- Pas de sélection multiple pour traitement en masse
- Wizard 10 étapes pour configuration basique

#### Bonnes pratiques
- One-click actions pour tâches courantes
- Mémorisation choix précédents
- Batch operations (sélectionner tout)
- Progressive disclosure (masquer complexité)

---

### 2.3 Densité Informationnelle

#### Principe
Ne présenter que l'information pertinente au contexte, éviter la surcharge.

#### Critères de vérification
- **Focus** : Une tâche principale par écran
- **Hiérarchie** : Info primaire > secondaire > tertiaire
- **Progressive disclosure** : Détails cachés par défaut
- **Pas de superflu** : Chaque élément a une fonction

#### Exemples de violations
- Dashboard avec 30 widgets
- Tous les paramètres avancés visibles d'emblée
- Texte d'aide omniprésent masquant contenu
- Formulaire avec 40 champs sur une page

#### Bonnes pratiques
- Afficher top 5-7 éléments essentiels
- "Show more" pour détails
- Tabs/accordions pour organisation
- Masquer fonctions avancées dans menus secondaires

---

## DIMENSION 3 : CONTRÔLE EXPLICITE

L'utilisateur doit garder le contrôle du système.

### 3.1 Actions Explicites

#### Principe
Le système doit exécuter uniquement les actions explicitement demandées par l'utilisateur.

#### Critères de vérification
- **Validation explicite** : Bouton "Valider", "Enregistrer" requis
- **Pas d'auto-submit** : Formulaires soumis seulement si demandé
- **Confirmations** : Actions critiques nécessitent confirmation
- **Transparence** : Utilisateur comprend ce qui va se passer

#### Exemples de violations
- Formulaire auto-submit au changement de select
- Redirection automatique sans prévenir
- Sauvegarde automatique modifiant état sans consentement
- Actions déclenchées par hover non intentionnel

#### Bonnes pratiques
- Boutons d'action clairs pour chaque opération
- Preview avant application (filtres, suppressions)
- "Êtes-vous sûr ?" pour actions irréversibles
- Confirmation explicite pour sortie avec données non sauvegardées

---

### 3.2 Contrôle Utilisateur

#### Principe
L'utilisateur doit pouvoir contrôler le déroulement du système (interrompre, annuler, reprendre).

#### Critères de vérification
- **Annulation** : Undo/redo, boutons "Annuler"
- **Interruption** : Possibilité de stopper opérations longues
- **Navigation libre** : Pas de parcours forcé
- **Récupération** : États sauvegardés, brouillons

#### Exemples de violations
- Pas de bouton "Annuler" dans dialog
- Upload non interruptible
- Wizard sans retour arrière possible
- Perte de données si navigation arrière

#### Bonnes pratiques
- Bouton "Annuler" dans toutes les modals
- Cancel button pour opérations longues
- Breadcrumbs cliquables
- Auto-save drafts
- Ctrl+Z universel

---

## DIMENSION 4 : ADAPTABILITÉ

Capacité du système à s'adapter à l'utilisateur et au contexte.

### 4.1 Flexibilité

#### Principe
Offrir plusieurs moyens d'accomplir une tâche pour s'adapter aux différents types d'utilisateurs.

#### Critères de vérification
- **Chemins multiples** : UI + raccourcis clavier + CLI
- **Personnalisation** : Dashboards, favoris, préférences
- **Modes** : Novice vs expert
- **Accessibilité** : Clavier + souris + touch + voix

#### Exemples de violations
- Une seule méthode pour accomplir action
- Pas de raccourcis clavier
- Interface figée non personnalisable
- Navigation souris uniquement

#### Bonnes pratiques
- Shortcuts clavier pour power users
- Customizable toolbars/sidebars
- Quick actions (right-click menus)
- Modes d'affichage (liste, grille, kanban)
- Responsive pour multi-devices

---

### 4.2 Prise en Compte de l'Expérience Utilisateur

#### Principe
Le système doit distinguer utilisateurs novices et experts, s'adapter à leur niveau.

#### Critères de vérification
- **Onboarding** : Tutoriels pour nouveaux utilisateurs
- **Découverte progressive** : Fonctionnalités avancées masquées initialement
- **Aide contextuelle** : Tooltips, hints pour novices
- **Efficacité experts** : Shortcuts, bulk actions pour avancés

#### Exemples de violations
- Même interface complexe pour tous
- Pas d'onboarding pour nouveaux utilisateurs
- Fonctionnalités cachées sans documentation
- Pas de mode "avancé"

#### Bonnes pratiques
- Welcome tour interactif
- Progressive disclosure (basique → avancé)
- Tooltips optionnels (masquables)
- "Advanced mode" toggle
- Recently used / frequently used items

---

## DIMENSION 5 : GESTION DES ERREURS

Aider l'utilisateur à éviter, détecter et corriger les erreurs.

### 5.1 Protection contre les Erreurs

#### Principe
Prévenir les erreurs avant qu'elles se produisent.

#### Critères de vérification
- **Validation proactive** : Désactivation d'options invalides
- **Contraintes** : Input masking, formats forcés
- **Confirmations** : Double-vérification actions critiques
- **Defaults sûrs** : Choix par défaut évitant erreurs

#### Exemples de violations
- Bouton "Supprimer" sans confirmation
- Champs acceptant tout format sans validation
- Actions destructives trop faciles à déclencher
- Pas de disabled states

#### Bonnes pratiques
- Disabled buttons pour actions non disponibles
- Input types HTML5 (email, tel, date)
- Confirmation modale : "Supprimer définitivement X ?"
- Undo window (5s pour annuler action)
- Validation temps réel

---

### 5.2 Qualité des Messages d'Erreur

#### Principe
Messages d'erreur clairs, précis, constructifs, en langage utilisateur.

#### Critères de vérification
- **Clarté** : Langage simple, pas de jargon technique
- **Précision** : Localisation exacte du problème
- **Explication** : Pourquoi c'est une erreur
- **Solution** : Comment corriger
- **Ton** : Pas de blâme, empathique

#### Exemples de violations
- "Error 500"
- "Invalid input" sans préciser quel champ
- Messages techniques : "NullPointerException"
- Ton accusateur : "Vous avez mal saisi"

#### Bonnes pratiques
- "Le mot de passe doit contenir minimum 8 caractères, 1 majuscule et 1 chiffre"
- Surligner champ en erreur
- Icône + message + lien aide
- Ton : "Ce format n'est pas reconnu. Essayez : nom@domaine.com"
- Suggestions : "Vouliez-vous dire [suggestion] ?"

---

### 5.3 Correction des Erreurs

#### Principe
Faciliter la correction des erreurs détectées.

#### Critères de vérification
- **Undo/Redo** : Annulation simple
- **Conservation saisie** : Garder données valides après erreur
- **Focus automatique** : Curseur sur champ en erreur
- **Récupération** : Corbeille, versioning

#### Exemples de violations
- Formulaire vidé après erreur de validation
- Message d'erreur sans indication de localisation
- Suppression définitive sans récupération possible
- Pas de focus sur champ problématique

#### Bonnes pratiques
- Conserver toutes valeurs valides après erreur
- Scroll + focus sur premier champ invalide
- Corbeille avec récupération 30 jours
- Ctrl+Z pour annuler
- Autocorrection suggestions

---

## DIMENSION 6 : HOMOGÉNÉITÉ/COHÉRENCE

Cohérence du design à travers l'interface.

### 6.1 Cohérence Interne

#### Principe
Mêmes codes (terminologie, graphismes, procédures) pour mêmes situations dans toute l'application.

#### Critères de vérification
- **Terminologie** : Vocabulaire uniforme partout
- **UI patterns** : Composants identiques pour fonctions similaires
- **Interactions** : Comportements prévisibles
- **Design tokens** : Couleurs, spacing, typography cohérents

#### Exemples de violations
- "Enregistrer" sur une page, "Sauvegarder" ailleurs
- Bouton primaire bleu ici, vert là
- Icône × ferme modal ici, annule action là
- Layouts différents sans raison

#### Bonnes pratiques
- Design system documenté
- Glossaire de terminologie (Style Guide)
- Component library partagée
- Design tokens (CSS variables)
- Audit régulier cohérence

---

### 6.2 Cohérence Externe

#### Principe
Respecter les conventions de la plateforme et standards de l'industrie.

#### Critères de vérification
- **Standards OS** : iOS HIG, Material Design, Windows guidelines
- **Conventions web** : Logo top-left = home, hamburger = menu
- **Patterns reconnus** : Swipe to delete, pull to refresh
- **Accessibilité** : WCAG, ARIA standards

#### Exemples de violations
- Comportements contraires aux attentes plateforme
- Réinventer patterns existants sans raison
- Ignorer conventions universelles
- Non-respect standards accessibilité

#### Bonnes pratiques
- Suivre Human Interface Guidelines (iOS)
- Respecter Material Design (Android)
- Patterns natifs plateforme (navigation, gestures)
- WCAG 2.1 AA minimum
- Conventions web (underlined links, breadcrumbs)

---

## DIMENSION 7 : SIGNIFIANCE DES CODES

Les codes et dénominations doivent être significatifs pour l'utilisateur.

### 7.1 Signifiance des Labels et Intitulés

#### Principe
Les termes, labels et icônes doivent avoir un sens évident pour l'utilisateur cible.

#### Critères de vérification
- **Langage métier** : Terminologie du domaine utilisateur
- **Clarté** : Pas d'ambiguïté sur fonction
- **Icônes universelles** : Symboles reconnus
- **Localisation** : Adapté à langue et culture

#### Exemples de violations
- Jargon technique incompréhensible
- Icônes abstraites sans correspondance
- Termes génériques : "Item", "Element"
- Anglicismes non maîtrisés par cible

#### Bonnes pratiques
- Vocabulaire du domaine utilisateur
- Labels descriptifs : "Mes factures" vs "Documents"
- Icônes standard (enveloppe = email, corbeille = delete)
- Icônes + text labels
- Tests utilisateurs pour vérifier compréhension

---

### 7.2 Signifiance des Informations Affichées

#### Principe
Les informations présentées doivent être pertinentes et compréhensibles.

#### Critères de vérification
- **Pertinence** : Info utile au contexte actuel
- **Format adapté** : Unités, formats selon audience
- **Contexte fourni** : Pas de données brutes sans explication
- **Pas de codes** : Éviter identifiants techniques

#### Exemples de violations
- Afficher ID technique au lieu de nom lisible
- Timestamps Unix au lieu de dates relatives
- Statuts codés ("ST_003") sans légende
- Données sans unités ou contexte

#### Bonnes pratiques
- Noms compréhensibles au lieu d'IDs
- Dates relatives ("il y a 2h" vs "14:32:18")
- Statuts en clair avec couleur
- Unités explicites (€, km, %)
- Tooltips pour données complexes

---

## Utilisation de ce Framework

### Grille d'Évaluation

Évaluer chaque critère sur échelle 1-5 :
- **1** : Conforme, aucun problème
- **2** : Violations mineures, impact limité
- **3** : Violations modérées, améliorations recommandées
- **4** : Violations importantes, impact significatif
- **5** : Violations critiques, problème majeur

### Matrice de Scoring

| Dimension | Critères | Score Moyen | Priorité |
|-----------|----------|-------------|----------|
| 1. Guidage | 1.1 à 1.5 | /5 | |
| 2. Charge de Travail | 2.1 à 2.3 | /5 | |
| 3. Contrôle Explicite | 3.1 à 3.2 | /5 | |
| 4. Adaptabilité | 4.1 à 4.2 | /5 | |
| 5. Gestion Erreurs | 5.1 à 5.3 | /5 | |
| 6. Homogénéité | 6.1 à 6.2 | /5 | |
| 7. Signifiance | 7.1 à 7.2 | /5 | |

### Heat Map

Visualiser violations par dimension pour identifier faiblesses majeures :
- 🟢 Score 1-2 : Conforme
- 🟡 Score 2.5-3.5 : Améliorations souhaitables
- 🟠 Score 3.5-4.5 : Corrections importantes
- 🔴 Score > 4.5 : Critiques prioritaires

### Complémentarité avec Nielsen

Bastien & Scapin est complémentaire aux 10 heuristiques de Nielsen :
- **Plus granulaire** : 18 critères vs 10 heuristiques
- **Perspective européenne** : Approche francophone, référence INRIA
- **Focus charge cognitive** : Dimension "Charge de Travail" détaillée
- **Adaptabilité explicite** : Flexibilité et expérience utilisateur séparées

**Recommandation** : Utiliser les deux frameworks en parallèle pour audit complet.

---

## Sources

- Bastien, J.M.C. & Scapin, D.L. (1993). "Ergonomic Criteria for the Evaluation of Human-Computer Interfaces". INRIA Technical Report N° 156.
- Scapin, D.L. & Bastien, J.M.C. (1997). "Ergonomic criteria for evaluating the ergonomic quality of interactive systems". Behaviour & Information Technology, 16(4-5).
- Version révisée et complétée (2001-2004) : https://www.lamsade.dauphine.fr/~manouvri/IHM/Bastien-Scapin.pdf
