# WCAG Accessibility Checklist

> Checklist interactive pour évaluer la conformité WCAG 2.1/2.2.
> Cocher les critères conformes, documenter les violations.

---

## Header

| Champ | Valeur |
|-------|--------|
| **Projet/Interface** | [Nom] |
| **URL/Scope** | [URL ou description du scope] |
| **Niveau cible** | [ ] A / [ ] AA / [ ] AAA |
| **Date audit** | [YYYY-MM-DD] |
| **Auditeur** | [Nom] |
| **Outils utilisés** | [axe, WAVE, Lighthouse, VoiceOver, etc.] |

---

## Résumé

### Score de Conformité

| Niveau | Total Critères | Conformes | Non-conformes | N/A | % |
|--------|----------------|-----------|---------------|-----|---|
| **A** | 30 | [ ] | [ ] | [ ] | [ ]% |
| **AA** | 20 | [ ] | [ ] | [ ] | [ ]% |
| **AAA** | 28 | [ ] | [ ] | [ ] | [ ]% |

### Statut Global

- [ ] 🟢 **Conforme niveau A** (100% critères A passent)
- [ ] 🟢 **Conforme niveau AA** (100% critères A + AA passent)
- [ ] 🟡 **Partiellement conforme** (quelques violations)
- [ ] 🔴 **Non conforme** (violations critiques)

---

## Principe 1 : PERCEIVABLE (Perceptible)

### 1.1 Text Alternatives

#### 1.1.1 Non-text Content (A)

**Critère :** Tout contenu non textuel a une alternative textuelle équivalente.

| Test | Statut | Notes |
|------|--------|-------|
| Images informatives ont alt descriptif | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Images décoratives ont alt="" ou role="presentation" | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Icônes ont aria-label ou texte caché | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Boutons image ont alt ou aria-label | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| CAPTCHAs ont alternative | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Graphiques/charts ont description | ☐ ✅ / ☐ ❌ / ☐ N/A | |

**Violations :**
| Élément | Description | Sévérité | Fix |
|---------|-------------|----------|-----|
| | | | |

---

### 1.2 Time-based Media

#### 1.2.1 Audio-only and Video-only (Prerecorded) (A)

| Test | Statut | Notes |
|------|--------|-------|
| Audio préenregistré a transcription | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Vidéo sans audio a alternative texte ou audio | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 1.2.2 Captions (Prerecorded) (A)

| Test | Statut | Notes |
|------|--------|-------|
| Vidéos ont sous-titres | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Sous-titres synchronisés | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Sous-titres incluent sons significatifs | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 1.2.3 Audio Description or Media Alternative (Prerecorded) (A)

| Test | Statut | Notes |
|------|--------|-------|
| Vidéos ont audiodescription ou alternative | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 1.2.4 Captions (Live) (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Contenu live a sous-titres temps réel | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 1.2.5 Audio Description (Prerecorded) (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Audiodescription fournie pour vidéos | ☐ ✅ / ☐ ❌ / ☐ N/A | |

---

### 1.3 Adaptable

#### 1.3.1 Info and Relationships (A)

| Test | Statut | Notes |
|------|--------|-------|
| Headings utilisent balises H1-H6 | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Hiérarchie headings logique (pas de saut) | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Listes utilisent ul/ol/dl | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Tableaux ont th et scope | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Formulaires ont labels associés (for/id) | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Groupes de champs utilisent fieldset/legend | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Régions ont landmarks ARIA | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 1.3.2 Meaningful Sequence (A)

| Test | Statut | Notes |
|------|--------|-------|
| Ordre DOM correspond à ordre visuel | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| CSS off : contenu reste logique | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 1.3.3 Sensory Characteristics (A)

| Test | Statut | Notes |
|------|--------|-------|
| Instructions ne reposent pas uniquement sur forme/couleur/position | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 1.3.4 Orientation (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Pas de lock orientation (portrait/landscape) | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 1.3.5 Identify Input Purpose (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Champs personnels ont autocomplete | ☐ ✅ / ☐ ❌ / ☐ N/A | |

---

### 1.4 Distinguishable

#### 1.4.1 Use of Color (A)

| Test | Statut | Notes |
|------|--------|-------|
| Info pas uniquement par couleur | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Liens distingués autrement que par couleur | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Erreurs indiquées autrement que par couleur | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 1.4.2 Audio Control (A)

| Test | Statut | Notes |
|------|--------|-------|
| Audio auto-play contrôlable ou <3s | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 1.4.3 Contrast (Minimum) (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Texte normal : ratio ≥ 4.5:1 | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Texte large (≥18pt ou ≥14pt bold) : ratio ≥ 3:1 | ☐ ✅ / ☐ ❌ / ☐ N/A | |

**Violations contraste :**
| Élément | Foreground | Background | Ratio | Requis |
|---------|------------|------------|-------|--------|
| | | | | |

#### 1.4.4 Resize Text (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Zoom 200% : contenu lisible | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Zoom 200% : pas de perte de fonctionnalité | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 1.4.5 Images of Text (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Pas de texte en image (sauf logo) | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 1.4.10 Reflow (AA)

| Test | Statut | Notes |
|------|--------|-------|
| À 320px : pas de scroll horizontal | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 1.4.11 Non-text Contrast (AA)

| Test | Statut | Notes |
|------|--------|-------|
| UI components : ratio ≥ 3:1 | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Icônes significatives : ratio ≥ 3:1 | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Focus indicator : ratio ≥ 3:1 | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 1.4.12 Text Spacing (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Override spacing : pas de perte contenu | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 1.4.13 Content on Hover or Focus (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Tooltips : dismissable (Escape) | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Tooltips : hoverable | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Tooltips : persistent | ☐ ✅ / ☐ ❌ / ☐ N/A | |

---

## Principe 2 : OPERABLE (Utilisable)

### 2.1 Keyboard Accessible

#### 2.1.1 Keyboard (A)

| Test | Statut | Notes |
|------|--------|-------|
| Tous éléments interactifs accessibles Tab | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Tous éléments activables Enter/Space | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Menus navigables avec flèches | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Custom widgets fonctionnent au clavier | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 2.1.2 No Keyboard Trap (A)

| Test | Statut | Notes |
|------|--------|-------|
| Pas de trap clavier (Tab sort de tous éléments) | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Modals : Escape ferme | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Modals : focus retourne au trigger | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 2.1.4 Character Key Shortcuts (A)

| Test | Statut | Notes |
|------|--------|-------|
| Shortcuts single-key : désactivables ou remappables | ☐ ✅ / ☐ ❌ / ☐ N/A | |

---

### 2.2 Enough Time

#### 2.2.1 Timing Adjustable (A)

| Test | Statut | Notes |
|------|--------|-------|
| Timeouts : avertissement + extension | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Ou timeout désactivable | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 2.2.2 Pause, Stop, Hide (A)

| Test | Statut | Notes |
|------|--------|-------|
| Animations : mécanisme pause/stop | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Carousels : contrôles pause | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Auto-refresh : contrôlable | ☐ ✅ / ☐ ❌ / ☐ N/A | |

---

### 2.3 Seizures and Physical Reactions

#### 2.3.1 Three Flashes or Below Threshold (A)

| Test | Statut | Notes |
|------|--------|-------|
| Pas de flash >3/seconde | ☐ ✅ / ☐ ❌ / ☐ N/A | |

---

### 2.4 Navigable

#### 2.4.1 Bypass Blocks (A)

| Test | Statut | Notes |
|------|--------|-------|
| Skip link vers contenu principal | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Skip link visible au focus | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 2.4.2 Page Titled (A)

| Test | Statut | Notes |
|------|--------|-------|
| Chaque page a title descriptif unique | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 2.4.3 Focus Order (A)

| Test | Statut | Notes |
|------|--------|-------|
| Ordre focus logique (top→bottom, left→right) | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Modals : focus trap approprié | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 2.4.4 Link Purpose (In Context) (A)

| Test | Statut | Notes |
|------|--------|-------|
| Liens ont texte descriptif (pas "cliquez ici") | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Ou contexte clarifie la destination | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 2.4.5 Multiple Ways (AA)

| Test | Statut | Notes |
|------|--------|-------|
| 2+ moyens de navigation (menu, search, sitemap) | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 2.4.6 Headings and Labels (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Headings décrivent le contenu | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Labels décrivent le champ | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 2.4.7 Focus Visible (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Focus visible sur tous éléments interactifs | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Focus suffisamment contrasté | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 2.4.11 Focus Not Obscured (Minimum) (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Focus pas caché par sticky elements | ☐ ✅ / ☐ ❌ / ☐ N/A | |

---

### 2.5 Input Modalities

#### 2.5.1 Pointer Gestures (A)

| Test | Statut | Notes |
|------|--------|-------|
| Gestes multipoint ont alternative single pointer | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 2.5.2 Pointer Cancellation (A)

| Test | Statut | Notes |
|------|--------|-------|
| Actions sur up-event (pas down-event) | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 2.5.3 Label in Name (A)

| Test | Statut | Notes |
|------|--------|-------|
| Accessible name contient le texte visible | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 2.5.4 Motion Actuation (A)

| Test | Statut | Notes |
|------|--------|-------|
| Motion a alternative UI (ou désactivable) | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 2.5.7 Dragging Movements (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Drag & drop a alternative single pointer | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 2.5.8 Target Size (Minimum) (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Touch targets ≥ 24×24px | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Ou spacing suffisant entre targets | ☐ ✅ / ☐ ❌ / ☐ N/A | |

---

## Principe 3 : UNDERSTANDABLE (Compréhensible)

### 3.1 Readable

#### 3.1.1 Language of Page (A)

| Test | Statut | Notes |
|------|--------|-------|
| `<html lang="fr">` présent | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 3.1.2 Language of Parts (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Passages en autre langue ont lang="xx" | ☐ ✅ / ☐ ❌ / ☐ N/A | |

---

### 3.2 Predictable

#### 3.2.1 On Focus (A)

| Test | Statut | Notes |
|------|--------|-------|
| Focus ne déclenche pas de changement contexte | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 3.2.2 On Input (A)

| Test | Statut | Notes |
|------|--------|-------|
| Changement input ne déclenche pas de changement contexte | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| (Ou utilisateur prévenu) | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 3.2.3 Consistent Navigation (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Navigation dans même ordre sur toutes pages | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 3.2.4 Consistent Identification (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Même fonctionnalité = même label | ☐ ✅ / ☐ ❌ / ☐ N/A | |

---

### 3.3 Input Assistance

#### 3.3.1 Error Identification (A)

| Test | Statut | Notes |
|------|--------|-------|
| Erreurs identifiées en texte | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Champ en erreur identifié | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| aria-invalid="true" sur champs erreur | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 3.3.2 Labels or Instructions (A)

| Test | Statut | Notes |
|------|--------|-------|
| Tous inputs ont labels | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Format requis indiqué | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Required marqué | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 3.3.3 Error Suggestion (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Suggestions de correction fournies | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 3.3.4 Error Prevention (Legal, Financial, Data) (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Actions critiques : reversible/checked/confirmed | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 3.3.7 Redundant Entry (A)

| Test | Statut | Notes |
|------|--------|-------|
| Info déjà saisie : auto-populated ou selectable | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 3.3.8 Accessible Authentication (Minimum) (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Auth sans test cognitif (ou alternative) | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Copy-paste autorisé pour codes | ☐ ✅ / ☐ ❌ / ☐ N/A | |

---

## Principe 4 : ROBUST (Robuste)

### 4.1 Compatible

#### 4.1.2 Name, Role, Value (A)

| Test | Statut | Notes |
|------|--------|-------|
| ARIA roles corrects sur custom widgets | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| ARIA states corrects (expanded, pressed, etc.) | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Pas de duplicate IDs | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| axe-core : 0 violations | ☐ ✅ / ☐ ❌ / ☐ N/A | |

#### 4.1.3 Status Messages (AA)

| Test | Statut | Notes |
|------|--------|-------|
| Messages status annoncés (aria-live) | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Erreurs form annoncées (role="alert") | ☐ ✅ / ☐ ❌ / ☐ N/A | |
| Progress updates annoncés | ☐ ✅ / ☐ ❌ / ☐ N/A | |

---

## Tests Manuels Supplémentaires

### Screen Reader Testing

| Screen Reader | Test | Statut | Notes |
|---------------|------|--------|-------|
| **VoiceOver (Mac)** | Navigation headings | ☐ ✅ / ☐ ❌ | |
| | Lecture liens | ☐ ✅ / ☐ ❌ | |
| | Formulaires | ☐ ✅ / ☐ ❌ | |
| | Tables | ☐ ✅ / ☐ ❌ | |
| **NVDA (Windows)** | Navigation headings | ☐ ✅ / ☐ ❌ | |
| | Lecture liens | ☐ ✅ / ☐ ❌ | |
| | Formulaires | ☐ ✅ / ☐ ❌ | |

### Keyboard Only Testing

| Test | Statut | Notes |
|------|--------|-------|
| Naviguer tout le site au clavier | ☐ ✅ / ☐ ❌ | |
| Compléter un formulaire au clavier | ☐ ✅ / ☐ ❌ | |
| Utiliser les menus au clavier | ☐ ✅ / ☐ ❌ | |
| Ouvrir/fermer modals au clavier | ☐ ✅ / ☐ ❌ | |

---

## Violations Summary

### Par Sévérité

#### 🔴 Critiques (Bloquants)

| # | Critère | Élément | Description | Fix |
|---|---------|---------|-------------|-----|
| 1 | | | | |
| 2 | | | | |

#### 🟠 Sérieuses (Impact significatif)

| # | Critère | Élément | Description | Fix |
|---|---------|---------|-------------|-----|
| 1 | | | | |

#### 🟡 Mineures (Amélioration)

| # | Critère | Élément | Description | Fix |
|---|---------|---------|-------------|-----|
| 1 | | | | |

---

## Action Plan

### Immediate (Cette semaine)

- [ ] [Fix violation critique 1]
- [ ] [Fix violation critique 2]

### Short-term (Ce mois)

- [ ] [Fix violation sérieuse 1]
- [ ] [Fix violation sérieuse 2]

### Long-term (Ce trimestre)

- [ ] [Amélioration 1]
- [ ] [Amélioration 2]

---

## Metadata

| Champ | Valeur |
|-------|--------|
| **Date audit** | [YYYY-MM-DD] |
| **Auditeur** | [Nom] |
| **Version WCAG** | [ ] 2.1 / [ ] 2.2 |
| **Niveau cible** | [ ] A / [ ] AA / [ ] AAA |
| **Prochaine review** | [YYYY-MM-DD] |

---

*Checklist basée sur WCAG 2.1/2.2. Pour référence complète : `/frameworks/wcag-reference.md`*
