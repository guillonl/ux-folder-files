# Design Systems Reference - Guide Complet

## Introduction

Un **design system** est un ensemble de standards, composants, patterns et guidelines réutilisables permettant de construire des interfaces cohérentes, efficaces et de qualité à grande échelle.

Ce document couvre les fondamentaux des design systems en s'appuyant sur les best practices de **Material Design (Google)**, **Carbon (IBM)**, **Polaris (Shopify)**, et **Lightning (Salesforce)**.

---

## Structure d'un Design System

### Architecture en Couches

```
┌─────────────────────────────────────────┐
│           DOCUMENTATION                  │
│    Getting Started, Guidelines, Patterns │
├─────────────────────────────────────────┤
│              TEMPLATES                   │
│     Page layouts, Email, Dashboard       │
├─────────────────────────────────────────┤
│               PATTERNS                   │
│    Forms, Navigation, Search, Tables     │
├─────────────────────────────────────────┤
│             COMPONENTS                   │
│   Button, Input, Card, Modal, Table      │
├─────────────────────────────────────────┤
│              FOUNDATIONS                 │
│ Design Tokens: Colors, Typography, Space │
└─────────────────────────────────────────┘
```

---

## 1. Design Tokens

Les **design tokens** sont les atomes du design system : les valeurs de base (couleurs, typographie, espacements) stockées de façon centralisée et réutilisable.

### 1.1 Taxonomie des Tokens

#### Tokens Primitifs (Raw Values)

Valeurs brutes sans contexte sémantique.

```json
{
  "color": {
    "blue": {
      "50": "#E3F2FD",
      "100": "#BBDEFB",
      "200": "#90CAF9",
      "300": "#64B5F6",
      "400": "#42A5F5",
      "500": "#2196F3",
      "600": "#1E88E5",
      "700": "#1976D2",
      "800": "#1565C0",
      "900": "#0D47A1"
    },
    "gray": {
      "50": "#FAFAFA",
      "100": "#F5F5F5",
      "...": "..."
    }
  }
}
```

#### Tokens Sémantiques (Semantic)

Valeurs avec signification contextuelle.

```json
{
  "color": {
    "primary": "{color.blue.500}",
    "primary-hover": "{color.blue.600}",
    "primary-active": "{color.blue.700}",
    "secondary": "{color.gray.600}",
    "error": "{color.red.500}",
    "success": "{color.green.500}",
    "warning": "{color.orange.500}",
    "info": "{color.blue.400}"
  }
}
```

#### Tokens de Composant (Component)

Valeurs spécifiques aux composants.

```json
{
  "button": {
    "primary": {
      "background": "{color.primary}",
      "background-hover": "{color.primary-hover}",
      "text": "{color.on-primary}",
      "border-radius": "{radius.md}"
    }
  }
}
```

### 1.2 Color Tokens

#### Structure Recommandée

```
Colors/
├── Primitives/
│   ├── Blue (50-900)
│   ├── Gray (50-900)
│   ├── Red (50-900)
│   ├── Green (50-900)
│   ├── Orange (50-900)
│   └── ...
├── Semantic/
│   ├── Primary
│   ├── Secondary
│   ├── Error
│   ├── Success
│   ├── Warning
│   └── Info
├── Surface/
│   ├── Background
│   ├── Surface
│   ├── Surface-variant
│   └── Overlay
├── Text/
│   ├── Primary
│   ├── Secondary
│   ├── Disabled
│   ├── On-primary
│   ├── On-secondary
│   └── On-surface
└── Border/
    ├── Default
    ├── Focus
    └── Error
```

#### Dark Mode Strategy

**Approche 1 : Inversion sémantique**
```json
{
  "light": {
    "background": "#FFFFFF",
    "surface": "#F5F5F5",
    "text-primary": "#212121"
  },
  "dark": {
    "background": "#121212",
    "surface": "#1E1E1E",
    "text-primary": "#FFFFFF"
  }
}
```

**Approche 2 : Surface elevation (Material Design 3)**
```json
{
  "dark": {
    "surface-0": "#121212",
    "surface-1": "#1E1E1E",  /* +5% white overlay */
    "surface-2": "#232323",  /* +8% white overlay */
    "surface-3": "#282828",  /* +11% white overlay */
    "surface-4": "#2D2D2D"   /* +14% white overlay */
  }
}
```

#### Accessibilité Couleurs

| Combinaison | Ratio Min AA | Ratio Min AAA |
|-------------|--------------|---------------|
| Texte normal | 4.5:1 | 7:1 |
| Texte large (≥18pt) | 3:1 | 4.5:1 |
| UI Components | 3:1 | - |

### 1.3 Typography Tokens

#### Structure Recommandée

```json
{
  "typography": {
    "font-family": {
      "sans": "Inter, system-ui, sans-serif",
      "serif": "Georgia, serif",
      "mono": "JetBrains Mono, monospace"
    },
    "font-size": {
      "xs": "0.75rem",    /* 12px */
      "sm": "0.875rem",   /* 14px */
      "base": "1rem",     /* 16px */
      "lg": "1.125rem",   /* 18px */
      "xl": "1.25rem",    /* 20px */
      "2xl": "1.5rem",    /* 24px */
      "3xl": "1.875rem",  /* 30px */
      "4xl": "2.25rem",   /* 36px */
      "5xl": "3rem"       /* 48px */
    },
    "font-weight": {
      "regular": "400",
      "medium": "500",
      "semibold": "600",
      "bold": "700"
    },
    "line-height": {
      "tight": "1.25",
      "normal": "1.5",
      "relaxed": "1.75"
    },
    "letter-spacing": {
      "tight": "-0.025em",
      "normal": "0",
      "wide": "0.025em"
    }
  }
}
```

#### Type Scale (Composites)

```json
{
  "text-styles": {
    "display-large": {
      "font-family": "{font-family.sans}",
      "font-size": "3.5rem",
      "font-weight": "{font-weight.regular}",
      "line-height": "1.1",
      "letter-spacing": "-0.02em"
    },
    "headline-large": {
      "font-size": "2rem",
      "font-weight": "{font-weight.semibold}",
      "line-height": "1.25"
    },
    "title-large": {
      "font-size": "1.375rem",
      "font-weight": "{font-weight.medium}",
      "line-height": "1.3"
    },
    "body-large": {
      "font-size": "1rem",
      "font-weight": "{font-weight.regular}",
      "line-height": "1.5"
    },
    "label-large": {
      "font-size": "0.875rem",
      "font-weight": "{font-weight.medium}",
      "line-height": "1.4",
      "letter-spacing": "0.01em"
    },
    "caption": {
      "font-size": "0.75rem",
      "font-weight": "{font-weight.regular}",
      "line-height": "1.4"
    }
  }
}
```

### 1.4 Spacing Tokens

#### Grid System

**Base unit : 4px ou 8px**

```json
{
  "spacing": {
    "0": "0",
    "1": "0.25rem",   /* 4px */
    "2": "0.5rem",    /* 8px */
    "3": "0.75rem",   /* 12px */
    "4": "1rem",      /* 16px */
    "5": "1.25rem",   /* 20px */
    "6": "1.5rem",    /* 24px */
    "8": "2rem",      /* 32px */
    "10": "2.5rem",   /* 40px */
    "12": "3rem",     /* 48px */
    "16": "4rem",     /* 64px */
    "20": "5rem",     /* 80px */
    "24": "6rem"      /* 96px */
  }
}
```

#### Semantic Spacing

```json
{
  "spacing": {
    "component": {
      "padding-xs": "{spacing.2}",
      "padding-sm": "{spacing.3}",
      "padding-md": "{spacing.4}",
      "padding-lg": "{spacing.6}"
    },
    "layout": {
      "section-gap": "{spacing.16}",
      "page-margin": "{spacing.6}",
      "gutter": "{spacing.4}"
    }
  }
}
```

### 1.5 Elevation & Shadows

#### Elevation Scale

```json
{
  "elevation": {
    "0": "none",
    "1": "0 1px 2px 0 rgba(0, 0, 0, 0.05)",
    "2": "0 1px 3px 0 rgba(0, 0, 0, 0.1), 0 1px 2px -1px rgba(0, 0, 0, 0.1)",
    "3": "0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.1)",
    "4": "0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -4px rgba(0, 0, 0, 0.1)",
    "5": "0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 8px 10px -6px rgba(0, 0, 0, 0.1)",
    "6": "0 25px 50px -12px rgba(0, 0, 0, 0.25)"
  }
}
```

#### Usage Guidelines

| Level | Usage |
|-------|-------|
| 0 | Surfaces au repos |
| 1 | Cards, éléments légèrement surélevés |
| 2 | Dropdowns, menus |
| 3 | Modals, dialogs |
| 4 | Notifications, toasts |
| 5 | Overlays importants |

### 1.6 Border Radius

```json
{
  "radius": {
    "none": "0",
    "sm": "0.125rem",   /* 2px */
    "md": "0.25rem",    /* 4px */
    "lg": "0.5rem",     /* 8px */
    "xl": "0.75rem",    /* 12px */
    "2xl": "1rem",      /* 16px */
    "full": "9999px"    /* Pills, circles */
  }
}
```

### 1.7 Motion Tokens

```json
{
  "motion": {
    "duration": {
      "instant": "0ms",
      "fast": "100ms",
      "normal": "200ms",
      "slow": "300ms",
      "slower": "500ms"
    },
    "easing": {
      "linear": "linear",
      "ease-in": "cubic-bezier(0.4, 0, 1, 1)",
      "ease-out": "cubic-bezier(0, 0, 0.2, 1)",
      "ease-in-out": "cubic-bezier(0.4, 0, 0.2, 1)",
      "spring": "cubic-bezier(0.34, 1.56, 0.64, 1)"
    }
  }
}
```

#### Motion Principles

1. **Purposeful** : Animation sert un but (feedback, orientation, continuité)
2. **Focused** : Guide l'attention sans distraire
3. **Expressive** : Reflète la personnalité de la marque
4. **Quick** : Assez rapide pour ne pas bloquer l'utilisateur

---

## 2. Components

### 2.1 Core Components Inventory

#### Actions

| Component | Description | Variants |
|-----------|-------------|----------|
| **Button** | Action principale | Primary, Secondary, Tertiary, Ghost, Destructive |
| **IconButton** | Action iconique | Sizes: sm, md, lg |
| **Link** | Navigation textuelle | Standalone, Inline |
| **FAB** | Floating Action Button | Standard, Extended |

#### Inputs

| Component | Description | Variants |
|-----------|-------------|----------|
| **TextField** | Saisie texte simple | Outlined, Filled |
| **TextArea** | Saisie texte multi-ligne | - |
| **Select** | Sélection liste | Single, Multi |
| **Checkbox** | Sélection binaire | Default, Indeterminate |
| **Radio** | Sélection exclusive | - |
| **Switch** | Toggle on/off | - |
| **Slider** | Sélection range | Single, Range |
| **DatePicker** | Sélection date | Date, DateTime, Range |

#### Navigation

| Component | Description | Variants |
|-----------|-------------|----------|
| **Tabs** | Navigation dans page | Horizontal, Vertical |
| **Navbar** | Navigation principale | - |
| **Sidebar** | Navigation latérale | Collapsed, Expanded |
| **Breadcrumbs** | Fil d'Ariane | - |
| **Pagination** | Navigation pages | - |
| **Menu** | Menu contextuel | - |

#### Data Display

| Component | Description | Variants |
|-----------|-------------|----------|
| **Table** | Données tabulaires | Basic, Sortable, Selectable |
| **List** | Liste d'éléments | Simple, Complex |
| **Card** | Conteneur contenu | Elevated, Outlined |
| **Avatar** | Représentation user | Image, Initials, Icon |
| **Badge** | Indicateur compteur | Numeric, Dot |
| **Chip** | Tag/filtre | Assist, Filter, Input, Suggestion |
| **Tooltip** | Info contextuelle | - |

#### Feedback

| Component | Description | Variants |
|-----------|-------------|----------|
| **Alert** | Message important | Info, Success, Warning, Error |
| **Toast/Snackbar** | Notification temporaire | - |
| **Progress** | Indicateur progression | Linear, Circular |
| **Spinner** | Chargement indéterminé | - |
| **Skeleton** | Placeholder loading | - |

#### Overlay

| Component | Description | Variants |
|-----------|-------------|----------|
| **Modal/Dialog** | Contenu superposé | Sizes: sm, md, lg, fullscreen |
| **Drawer** | Panel latéral | Left, Right, Bottom |
| **Popover** | Contenu contextuel | - |
| **Dropdown** | Liste déroulante | - |

#### Layout

| Component | Description | Variants |
|-----------|-------------|----------|
| **Container** | Conteneur max-width | Sizes |
| **Grid** | Layout 12 colonnes | - |
| **Stack** | Layout flex | Horizontal, Vertical |
| **Divider** | Séparateur | Horizontal, Vertical |

### 2.2 Component API Standards

#### Naming Conventions

**Props communes :**

| Prop | Type | Usage |
|------|------|-------|
| `variant` | string | Style visuel (primary, secondary) |
| `size` | string | Dimension (sm, md, lg) |
| `disabled` | boolean | État désactivé |
| `loading` | boolean | État chargement |
| `className` | string | Classes CSS custom |
| `children` | ReactNode | Contenu |

**Events :**

| Event | Naming |
|-------|--------|
| Click | `onClick` |
| Change | `onChange` |
| Focus | `onFocus` |
| Blur | `onBlur` |
| Submit | `onSubmit` |

#### Exemple Button API

```tsx
interface ButtonProps {
  // Appearance
  variant?: 'primary' | 'secondary' | 'tertiary' | 'ghost' | 'destructive';
  size?: 'sm' | 'md' | 'lg';

  // States
  disabled?: boolean;
  loading?: boolean;

  // Content
  children: ReactNode;
  leftIcon?: ReactNode;
  rightIcon?: ReactNode;

  // Behavior
  type?: 'button' | 'submit' | 'reset';
  onClick?: (event: MouseEvent) => void;

  // Accessibility
  'aria-label'?: string;

  // Styling
  className?: string;
  fullWidth?: boolean;
}
```

### 2.3 Component States

#### États Requis

```
States/
├── Default (repos)
├── Hover (survol)
├── Focus (clavier)
├── Active/Pressed (click)
├── Disabled (inactif)
├── Loading (traitement)
├── Error (erreur)
├── Success (succès)
└── Selected (sélectionné)
```

#### Focus Visible

```css
/* Approche moderne */
:focus-visible {
  outline: 2px solid var(--color-primary);
  outline-offset: 2px;
}

:focus:not(:focus-visible) {
  outline: none;
}
```

### 2.4 Accessibility Requirements

Chaque composant DOIT :

- [ ] Être navigable au clavier (Tab, Enter, Escape, Arrows)
- [ ] Avoir focus visible
- [ ] Avoir ARIA roles/states corrects
- [ ] Avoir labels associés (inputs)
- [ ] Respecter contraste 4.5:1 (text) ou 3:1 (UI)
- [ ] Annoncer correctement aux screen readers

---

## 3. Patterns

### 3.1 Forms

#### Structure de Base

```
Form/
├── Form Header (titre, description)
├── Form Sections
│   ├── Section Title
│   ├── Fields (inputs, selects, etc.)
│   └── Section Help Text
├── Form Actions (submit, cancel)
└── Form Feedback (errors, success)
```

#### Validation Patterns

**Validation Inline (Recommandé) :**
- Valider au blur (perte focus)
- Afficher erreur sous le champ
- Utiliser `aria-invalid` et `aria-describedby`

```html
<label for="email">Email</label>
<input
  id="email"
  type="email"
  aria-invalid="true"
  aria-describedby="email-error"
>
<span id="email-error" role="alert">
  Format email invalide
</span>
```

**Error Summary (Pour formulaires longs) :**
- Liste d'erreurs en haut du formulaire
- Liens vers champs en erreur
- Focus automatique sur la liste

### 3.2 Navigation

#### Primary Navigation

```
┌─────────────────────────────────────────┐
│ Logo    Nav Items          User Menu    │
└─────────────────────────────────────────┘
```

#### Secondary Navigation (Sidebar)

```
┌────────┬────────────────────────────────┐
│ Logo   │                                │
├────────┤                                │
│ Nav 1  │                                │
│ Nav 2  │      Main Content              │
│ Nav 3  │                                │
│  └ Sub │                                │
│  └ Sub │                                │
│ Nav 4  │                                │
└────────┴────────────────────────────────┘
```

#### Mobile Navigation

- Hamburger menu (burger icon)
- Bottom navigation (2-5 items max)
- Tab bar

### 3.3 Data Tables

#### Features Standard

| Feature | Description |
|---------|-------------|
| Sorting | Click header pour trier |
| Filtering | Filtres par colonne ou globaux |
| Pagination | Navigation pages |
| Selection | Checkboxes pour actions bulk |
| Actions | Boutons par ligne |
| Empty State | Message quand pas de données |
| Loading State | Skeletons ou spinner |

#### Responsive Tables

**Approches :**
1. Horizontal scroll
2. Stacking (colonnes deviennent lignes)
3. Priority columns (cacher colonnes secondaires)

### 3.4 Empty States

#### Structure

```
┌─────────────────────────────────────┐
│                                     │
│           [Illustration]            │
│                                     │
│           Titre                     │
│       Description courte            │
│                                     │
│         [Primary Action]            │
│          [Secondary Action]         │
│                                     │
└─────────────────────────────────────┘
```

#### Types

| Type | Usage |
|------|-------|
| No data | Aucune donnée à afficher |
| No results | Recherche/filtre sans résultat |
| Error | Erreur de chargement |
| Permission | Accès non autorisé |
| First use | Onboarding, incitation à l'action |

### 3.5 Loading States

#### Patterns

| Pattern | Usage |
|---------|-------|
| Spinner | Chargement court, indéterminé |
| Skeleton | Chargement page/section |
| Progress bar | Chargement long, progression connue |
| Shimmer | Alternative skeleton |

#### Best Practices

- Spinner : <1s d'attente acceptable
- Skeleton : >1s, donne aperçu structure
- Progress : Opérations longues (upload, install)
- Message : >5s, informer l'utilisateur

---

## 4. Documentation

### 4.1 Structure Recommandée

```
Docs/
├── Getting Started/
│   ├── Installation
│   ├── Quick Start
│   └── Theming
├── Foundations/
│   ├── Colors
│   ├── Typography
│   ├── Spacing
│   ├── Elevation
│   └── Motion
├── Components/
│   ├── [Component Name]/
│   │   ├── Overview
│   │   ├── Props/API
│   │   ├── Examples
│   │   ├── Variants
│   │   ├── Accessibility
│   │   └── Guidelines (Do/Don't)
├── Patterns/
│   ├── Forms
│   ├── Navigation
│   ├── Tables
│   └── Loading
├── Resources/
│   ├── Figma Library
│   ├── Icon Library
│   └── Brand Assets
├── Contributing/
│   ├── How to Contribute
│   ├── Code Standards
│   └── Design Standards
└── Changelog
```

### 4.2 Component Documentation Template

```markdown
# [Component Name]

[Description courte du composant]

## Usage

[Quand utiliser ce composant]

## Import

```jsx
import { Component } from '@design-system/core';
```

## Basic Example

```jsx
<Component variant="primary">Label</Component>
```

[Interactive playground]

## Props

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| variant | 'primary' \| 'secondary' | 'primary' | Style visuel |
| size | 'sm' \| 'md' \| 'lg' | 'md' | Taille |
| disabled | boolean | false | État désactivé |

## Variants

### Primary
[Example + description]

### Secondary
[Example + description]

## States

### Disabled
[Example]

### Loading
[Example]

## Accessibility

- Keyboard: [Interactions clavier supportées]
- Screen readers: [Comportement attendu]
- ARIA: [Attributes utilisés]

## Guidelines

### Do ✅
- [Bonne pratique 1]
- [Bonne pratique 2]

### Don't ❌
- [Anti-pattern 1]
- [Anti-pattern 2]

## Related Components

- [Component A](link)
- [Component B](link)
```

---

## 5. Governance

### 5.1 Contribution Workflow

```
1. Issue/Request
   └── Bug report, Feature request, RFC

2. Triage
   └── DS team review, prioritization

3. Design (if needed)
   └── Figma specs, review with designer

4. Development
   └── Branch, implementation, tests

5. Code Review
   └── DS team review, accessibility check

6. Documentation
   └── Update docs, changelog

7. Release
   └── Semantic version, release notes
```

### 5.2 Versioning

**Semantic Versioning (SemVer) :**

```
MAJOR.MINOR.PATCH

MAJOR : Breaking changes
MINOR : New features (backward compatible)
PATCH : Bug fixes (backward compatible)
```

**Exemples :**
- `1.0.0` → `2.0.0` : Breaking change (API change, removal)
- `1.0.0` → `1.1.0` : New component ou feature
- `1.0.0` → `1.0.1` : Bug fix

### 5.3 Deprecation Policy

**Process :**

1. **Announcement** : Marquer comme deprecated (JSDoc, console warning)
2. **Migration Guide** : Documenter comment migrer
3. **Grace Period** : 2-3 minor versions avant suppression
4. **Removal** : Supprimer dans next major version

```tsx
/**
 * @deprecated Use `NewComponent` instead. Will be removed in v3.0.0
 */
export const OldComponent = () => {
  console.warn('OldComponent is deprecated. Use NewComponent instead.');
  // ...
};
```

### 5.4 Breaking Changes Guidelines

**Quand un breaking change est nécessaire :**
- Changement d'API (props renommées/supprimées)
- Changement de comportement
- Suppression de composant

**Process :**
1. RFC (Request for Comments) pour breaking changes majeurs
2. Communication claire (changelog, migration guide)
3. Codemods si possible (automated migration)
4. Support période de transition

---

## 6. Tools & Infrastructure

### 6.1 Design Tools

| Tool | Usage |
|------|-------|
| **Figma** | Design, prototyping, libraries |
| **Figma Tokens** | Sync tokens design ↔ code |
| **Storybook** | Documentation, playground |
| **Chromatic** | Visual regression testing |

### 6.2 Token Management

| Tool | Usage |
|------|-------|
| **Style Dictionary** | Token transformation (Amazon) |
| **Theo** | Token conversion (Salesforce) |
| **Tokens Studio** | Figma plugin for tokens |

**Style Dictionary Example :**

```json
// tokens/color.json
{
  "color": {
    "primary": {
      "value": "#2196F3",
      "type": "color"
    }
  }
}
```

```javascript
// config.js
module.exports = {
  source: ['tokens/**/*.json'],
  platforms: {
    css: {
      transformGroup: 'css',
      buildPath: 'dist/css/',
      files: [{
        destination: 'variables.css',
        format: 'css/variables'
      }]
    },
    js: {
      transformGroup: 'js',
      buildPath: 'dist/js/',
      files: [{
        destination: 'tokens.js',
        format: 'javascript/es6'
      }]
    }
  }
};
```

### 6.3 Testing

| Type | Tool | Usage |
|------|------|-------|
| Unit | Jest | Component logic |
| Integration | Testing Library | User interactions |
| Visual | Chromatic, Percy | Visual regressions |
| Accessibility | axe-core, jest-axe | A11y violations |

**Accessibility Testing Example :**

```typescript
import { axe, toHaveNoViolations } from 'jest-axe';

expect.extend(toHaveNoViolations);

test('Button should have no a11y violations', async () => {
  const { container } = render(<Button>Click me</Button>);
  const results = await axe(container);
  expect(results).toHaveNoViolations();
});
```

---

## 7. Benchmarks

### 7.1 Material Design (Google)

**Forces :**
- Documentation exhaustive
- Motion guidelines complètes
- Multi-platform (Web, Android, Flutter)
- Theming puissant (Material You)

**Structure tokens :**
- Primitive → Semantic → Component
- Color scheme avec tonal palettes
- Typography avec type scale définie

**URL :** https://m3.material.io/

### 7.2 Carbon (IBM)

**Forces :**
- Accessibilité AAA sur beaucoup de composants
- Data visualization guidelines
- Très structuré pour enterprise

**Particularités :**
- Grid 2x/16-column
- Motion avec principes physiques
- AI/Data components

**URL :** https://carbondesignsystem.com/

### 7.3 Polaris (Shopify)

**Forces :**
- Excellent content guidelines
- Focus e-commerce
- React components de haute qualité

**Particularités :**
- Tone and voice guidelines
- Merchant patterns
- Very opinionated (good for consistency)

**URL :** https://polaris.shopify.com/

### 7.4 Lightning (Salesforce)

**Forces :**
- Enterprise scale
- Accessibility focus
- CSS framework standalone (SLDS)

**Particularités :**
- Blueprint components
- Très complet pour CRM/B2B
- Multi-framework (React, LWC)

**URL :** https://www.lightningdesignsystem.com/

---

## 8. Maturity Model

### Levels

| Level | Name | Characteristics |
|-------|------|-----------------|
| 0 | **None** | Pas de DS, styles ad-hoc |
| 1 | **Emerging** | Tokens de base, quelques composants |
| 2 | **Growing** | Composants core, docs basic, adoption partielle |
| 3 | **Mature** | Composants complets, docs riches, gouvernance, adoption forte |
| 4 | **Leading** | Innovation, influence industrie, open source |

### Assessment Criteria

| Criteria | Level 1 | Level 2 | Level 3 | Level 4 |
|----------|---------|---------|---------|---------|
| Tokens | Basic | Structured | Semantic layers | Cross-platform |
| Components | <10 | 10-30 | 30-50+ | Complete |
| Docs | README | Basic docs | Rich docs | Exemplary |
| Adoption | <30% | 30-60% | 60-90% | >90% |
| Governance | None | Basic | Mature | Industry leading |

---

## Resources

### Learning
- [Design Systems Handbook](https://www.designbetter.co/design-systems-handbook) - InVision
- [Atomic Design](https://atomicdesign.bradfrost.com/) - Brad Frost
- [Design System Checklist](https://www.designsystemchecklist.com/)

### Tools
- [Figma](https://figma.com)
- [Storybook](https://storybook.js.org)
- [Style Dictionary](https://amzn.github.io/style-dictionary/)
- [Tokens Studio](https://tokens.studio)

### Communities
- [Design Systems Slack](https://design.systems/slack/)
- [Design Systems Reddit](https://reddit.com/r/designsystems)

---

## Version

- **Document version** : 1.0
- **Dernière mise à jour** : 2026-01
- **Références** : Material Design 3, Carbon, Polaris, Lightning

---

**Note** : Ce document est une référence. Pour l'audit d'un design system existant, utilisez l'agent `design-system-auditor.md`.
