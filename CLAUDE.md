# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Linear-inspired UI component library built with Next.js 14, React 18, TypeScript, and shadcn/ui. The project serves as a showcase/design system demonstrating various Radix UI components styled with Tailwind CSS.

## Development Commands

### Running the Application
- `npm run dev` - Start development server (default: http://localhost:3000)
- `npm run build` - Build production bundle
- `npm start` - Start production server
- `npm run lint` - Run ESLint

## Architecture

### Directory Structure
```
src/
├── app/                    # Next.js App Router
│   ├── layout.tsx         # Root layout with Inter font and Toaster
│   ├── page.tsx           # Home page showcasing all component demos
│   └── globals.css        # Global styles and CSS variables
├── components/
│   ├── ui/                # Base shadcn/ui components (Radix UI + Tailwind)
│   └── *Demo.tsx          # Demo/example components for each UI component
└── lib/
    └── utils.ts           # Utility functions (cn helper for class merging)
```

### Component Architecture
- **Base UI Components** (`src/components/ui/`): Reusable primitives built on Radix UI with Tailwind styling using `class-variance-authority` for variants
- **Demo Components** (`src/components/*Demo.tsx`): Example implementations showing how to use each UI component
- **Main Page** (`src/app/page.tsx`): Grid layout showcasing all demo components

### Key Patterns

#### Styling System
- Uses HSL-based CSS custom properties for theming (defined in globals.css)
- Tailwind config extends theme with semantic color tokens (primary, secondary, destructive, muted, accent, etc.)
- Dark mode supported via `class` strategy in Tailwind config
- `cn()` utility function combines `clsx` and `tailwind-merge` for conditional className merging

#### Component Variants
- UI components use `class-variance-authority` (cva) to define variants
- Example: Button component has `variant` (default, destructive, outline, secondary, ghost, link) and `size` (default, sm, lg, icon) props
- All UI components are built as forwarded refs for composition

#### Path Aliasing
- `@/*` maps to `./src/*` (configured in tsconfig.json)
- Always use path aliases for imports: `@/components/ui/button` instead of relative paths

### Technology Stack
- **Framework**: Next.js 14 (App Router)
- **UI Library**: shadcn/ui (composition of Radix UI primitives)
- **Styling**: Tailwind CSS with custom design tokens
- **Type Safety**: TypeScript with strict mode enabled
- **Icons**: Lucide React and Radix Icons
- **Additional**: TanStack Table for data tables, date-fns for date manipulation, cmdk for command palette

## Working with Components

### Adding New shadcn/ui Components
When adding new shadcn components, they should be placed in `src/components/ui/` and follow the existing pattern:
1. Use Radix UI primitives as base
2. Define variants using `cva`
3. Export TypeScript interfaces for props
4. Use `cn()` utility for className merging
5. Forward refs for composition support

### Creating Demo Components
Demo components go in `src/components/` and should:
1. Import from `@/components/ui/*`
2. Provide realistic usage examples
3. Be self-contained and showcase key features
4. Be added to the main grid layout in `src/app/page.tsx`
