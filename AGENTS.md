# AGENT CODING GUIDELINES

Last Updated: February 15, 2026

This repository contains a single Stylus-based UserCSS file for **Claude AI Chat** (claude.ai). All modifications must adhere to the existing style and structure.

## Target Domain

- **Primary Domain**: `claude.ai`
- **UserStyle applies to**: `@-moz-document domain("claude.ai")`

## 1. Build, Lint, and Test Commands

| Command | Description |
| :--- | :--- |
| **Lint** | `stylelint ClaudeChat-Gruvbox-Dark.user.css` (Recommended) |
| **Test** | None. Changes are verified visually on the target domain (claude.ai). |
| **Single Test** | N/A. |

## 2. Code Style and Conventions

### General Structure and Language
*   **Language:** Stylus is the required preprocessor (indicated by `@preprocessor stylus`).
*   **Formatting:** Use **4-space indentation**. Opening braces (`{`) must be on the same line as the selector.
*   **Specificity:** Use `!important` on almost every property to ensure overrides on the target site. Only omit it if the property is guaranteed to take effect without it.
*   **UserCSS Block:** Do not modify the `/* ==UserStyle== ... ==/UserStyle== */` block unless updating metadata or variables.
*   **Domain Scope:** All styles are wrapped in `@-moz-document domain("claude.ai")` block.

### Variables and Naming
*   **CSS Variables:** Use CSS variables (`--variable-name`) within `:root` blocks for defining colors, fonts, and other global values.
*   **Stylus Variables:** Use Stylus variables (`$variable-name = value`) for preprocessor logic and font aliases.
*   **Nesting:** Use Stylus nesting (`&:hover`, `&::before`, `.child-selector`) extensively for pseudo-classes and descendant selectors.
*   **Font Variables:** Reference font variables from `:root` block (e.g., `--font-GeistSans`, `--font-JetbrainsVar`).

### Color Palette (Gruvbox Dark Theme)
The theme uses the Gruvbox dark color scheme. Key colors:
*   **Backgrounds:** `--bg-dark` (#282828), `--bg-dark-new` (#1F1E1D), `--bg-def-dark` (#171718), `--shadow-bg` (#1d1b1a)
*   **Text:** `--text-white` (#f9f5d7), `--text-offwhite` (#fbf1c7), `--text--faded` (#d5c4a1), `--text--veryfade` (#928374)
*   **Accents:** `--faded-red` (#fb4934), `--faded-green` (#b8bb26), `--faded-blue` (#83a598), `--faded-yellow` (#fabd2f), `--faded-aqua` (#8ec07c), `--faded-purple` (#d3869b), `--faded-orange` (#fe8019)
*   **Borders:** `--bg2-dark` (#504945), `--bg3-dark` (#665c54), `--bg4-dark` (#7c6f64)

### Micro-interactions and Transitions
*   **Transitions:** All visual changes (color, background, transform) must be animated.
    *   **Timing:** Common timing functions are `ease-in-out` and `all 0.3s ease-in-out`.
    *   **Multi-property:** Use comma-separated transitions for multiple properties (e.g., `transition: background 0.6s ease-in-out, padding 0.22s ease-in-out`).
    *   **Cubic-Bezier:** Use `cubic-bezier(0.4, 0, 0.2, 1)` for smooth interactions (commonly used for buttons).
*   **Hover Effects:** Implement subtle hover effects using the following properties:
    *   `transform`: Used for scaling (`scale(1.02)`) or slight movement (`translateY(-1px)`).
    *   `text-shadow`: Used to add a glow effect to text.
    *   `box-shadow`: Used to add depth or glow to elements.
    *   `border-color`: Transition borders for interactive elements.

### Typography and Font Rendering
*   **Font Smoothing:** Apply the following properties to text elements for a polished look:
    ```css
    -webkit-font-smoothing: antialiased !important;
    -moz-osx-font-smoothing: grayscale !important;
    text-rendering: optimizeLegibility !important;
    ```
*   **Font Usage:** Use the defined CSS variables (e.g., `var(--font-GeistSans)`, `var(--font-JetbrainsVar)`) for font-family declarations.
*   **Font Imports:** Fonts are imported via `@font-face` from FontSource (cdn.jsdelivr.net) and OnlineWebFonts.

### Claude-Specific Selectors
Common selectors used for Claude UI:
*   **Query Bar:** `div.query-bar`
*   **Sidebar:** `.bg-sidebar`, `div[data-sidebar="header"]`
*   **Chat History:** `span.flex-1`
*   **Model Select:** `button#model-select-trigger`
*   **Buttons:** `button.inline-flex`, `button[data-slot="button"].inline-flex`
*   **Textarea:** `textarea`
*   **Code Blocks:** `span.text-sm.px-1.rounded-sm`, `code`, `.hljs-function`, `.hljs-class`
*   **Citations:** `button.citation>button`

### Button Styling Pattern
Pill-style buttons used throughout Claude UI:
```css
button.inline-flex {
    color: var(--text--faded) !important;
    background: var(--bg-dark-new) !important;
    border: 1px solid var(--bg2-dark) !important;
    border-radius: 9999px !important;
    padding: 0rem 1.25rem !important;
    font-size: 0.875rem !important;
    font-weight: 500 !important;
    cursor: pointer !important;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1) !important;

    &:hover {
        color: var(--faded-green) !important;
        background: var(--bg-def-dark) !important;
        border-color: var(--text--faded) !important;
        transform: translateY(-1px) !important;
        box-shadow: 0 5px 4px rgba(0, 0, 0, 0.1) !important;
    }
}
```

### UserCSS Variables
The style includes configurable options via UserCSS variables:
*   `noLogo` - Hide Claude logo
*   `noSideHeader` - Hide sidebar header
*   `LocalFont` - Use local placeholder font
*   `LoadWebFont` - Load font from web
*   `newfont` - Text font selection (Test Tiempos Text, Website Default, Geist Sans)
*   `headfont` - Heading font selection (Inherit, Bricolage Grotesque Variable)

### Commit Message Style
*   **Format:** Use a concise, single-line subject. The format should be `type: subject`.
*   **Type:** Use conventional commit types (e.g., `feat`, `fix`, `chore`, `style`, `refactor`, `docs`).
*   **Subject:** Focus on the area of change and what was done (e.g., `feat: add hover effects to sidebar buttons`).

### External Rules
*   **Rules:** No external Cursor or Copilot rules were found.
