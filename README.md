# Linear UI Kit

This is a [Linear](https://www.linear.app) UI Design using [Shadcn](https://https://ui.shadcn.com/).

<img width="1485" alt="thumbnail" src="https://github.com/marvkr/linear-shadcn/assets/88862495/68ccdc80-df3c-410f-b5ab-e3aa68272daf">

## Color System

This project uses a semantic color system defined in `src/app/globals.css`. Understanding these color variables will help you customize and extend the design system.

### Color Variables Overview

```css
--background: 234 17% 12%   ← Darkest - Base layer
--input:      217 32% 17%   ← Dark blue-gray - Input borders
--card:       236 18% 15%   ← Slightly elevated surfaces
--muted:      236 18% 15%   ← Same as card (separators/muted BGs)
--secondary:  231 20% 19%   ← Lighter - UI tracks & buttons
--accent:     236 13% 22%   ← Lightest - Hover/focus states
--border:     237 15% 26%   ← Lightest - General borders
```

### Visual Hierarchy

```
Darkest                                           Lightest
  ↓                                                   ↓
12%         15%         17%         19%       22%       26%
background  card/muted  input       secondary accent    border
    └─────────┴───────────┴────────────┴─────────┴────────┘
              Progressive elevation & interaction states
```

### Detailed Color Usage

#### **--background** & **--foreground**
```css
--background: 234 17% 12%  /* Dark blue-gray */
--foreground: 0 0% 100%    /* White */
```
- **Purpose:** The foundational dark layer of the entire app
- **Used for:** Body element background, base for inputs/buttons/dialogs/alerts
- The "canvas" everything sits on

#### **--card** & **--card-foreground**
```css
--card: 236 18% 15%        /* Slightly lighter than background */
--card-foreground: 210 40% 98%
```
- **Purpose:** Elevated surfaces for content containers
- **Used for:** Card component backgrounds, floating panels
- Creates visual hierarchy through subtle elevation

#### **--popover** & **--popover-foreground**
```css
--popover: 236 18% 15%     /* Same as card */
--popover-foreground: 0 0% 100%
```
- **Purpose:** All floating overlay panels
- **Used for:** Popover, dropdown menus, select dropdowns, command palettes
- Keeps floating elements consistent

#### **--primary** & **--primary-foreground**
```css
--primary: 235 100% 71%    /* Bright purple/blue */
--primary-foreground: 0 0% 100%
```
- **Purpose:** High-emphasis actions
- **Used for:** Default button variant, primary CTAs
- Draws user attention to main actions

#### **--secondary** & **--secondary-foreground**
```css
--secondary: 231 20% 19%   /* Dark blue-gray with border */
--secondary-foreground: 237 8% 56%  /* Muted gray text */
```
- **Purpose:** Low-emphasis interactive elements and UI tracks
- **Used for:**
  - Secondary variant buttons (less prominent than primary)
  - Slider tracks (the rail behind the thumb)
  - Progress bar backgrounds (unfilled portion)
  - Sheet close buttons, toast action hovers
- Creates subtle depth without drawing attention

#### **--muted** & **--muted-foreground**
```css
--muted: 236 18% 15%       /* Same as card/popover */
--muted-foreground: 229 9% 64%  /* Gray text */
```
- **Purpose:** Subdued elements and secondary text
- **--muted** used for: Divider lines in dropdowns/selects
- **--muted-foreground** heavily used for:
  - Card descriptions, dialog descriptions
  - Input placeholders
  - Secondary/explanatory text throughout

#### **--accent** & **--accent-foreground**
```css
--accent: 236 13% 22%      /* Slightly lighter gray for hover states */
--accent-foreground: 210 40% 98%
```
- **Purpose:** Universal hover/focus highlight color
- **Used for:**
  - Button hover states (ghost, outline variants)
  - Dropdown/select item hover and focus states
  - Any interactive element needing subtle highlight
- Provides consistent interaction feedback across the UI

#### **--destructive** & **--destructive-foreground**
```css
--destructive: 0 62.8% 30.6%  /* Dark red */
--destructive-foreground: 210 40% 98%
```
- **Purpose:** Dangerous/delete actions and error states
- **Used for:** Destructive button variant, error alerts
- Signals caution to users

#### **--border**
```css
--border: 237 15% 26%      /* Medium gray - lightest of the grays */
```
- **Purpose:** Default border color for ALL components
- **Used for:** Applied globally via `* { @apply border-border }`
- Creates visual boundaries between components
- Brightest gray to ensure visibility against dark backgrounds

#### **--input**
```css
--input: 217.2 32.6% 17.5%  /* Dark blue-gray */
```
- **Purpose:** Specific border color for form inputs
- **Used for:** Input fields, select triggers
- Distinguishes form fields from other bordered elements

#### **--ring**
```css
--ring: 235 100% 71%       /* Same as primary - bright purple/blue */
```
- **Purpose:** Focus indicator for keyboard navigation
- **Used for:** `focus-visible:ring-ring` on all focusable elements
- Accessibility feature for keyboard users

### Semantic Color Reference

| Variable | Purpose | When to use |
|----------|---------|-------------|
| **background** | Base canvas | Body, main surfaces at the bottom layer |
| **card/muted** | Slight elevation | Content containers, floating panels, dividers |
| **input** | Input distinction | Form field borders specifically |
| **secondary** | Low-emphasis elements | Track backgrounds, secondary buttons, inactive states |
| **accent** | Interaction feedback | Hover, focus, active states on interactive elements |
| **border** | Visual boundaries | Default borders to separate components |
| **primary** | Main actions | Primary buttons, important CTAs |
| **destructive** | Dangerous actions | Delete buttons, error states |

### Design Philosophy

The color system creates **visual depth** through progressive lightness values. In this dark theme, lighter shades signal:
- **Elevation** (floating elements)
- **Interactivity** (hover/focus states)
- **Hierarchy** (boundaries and separation)

Your eye naturally perceives lighter elements as "closer" or "more interactive" against the dark background, creating an intuitive visual hierarchy.
