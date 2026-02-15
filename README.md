# ClaudeChat-Gruvbox-Dark

A custom UserStyle for [claude.ai](https://claude.ai) that applies a beautiful Gruvbox-inspired dark theme with enhanced readability and modern UI improvements.

## Features

- **Gruvbox Color Palette**: Authentic Gruvbox dark color scheme with carefully selected background, text, and accent colors
- **Custom Fonts**: Premium font stack including `Geist Sans`, `Tiempos Text Regular`, `Geist Mono`, `JetBrains Mono`, and `Bricolage Grotesque Variable`
- **Smooth Animations**: All interactive elements feature polished micro-interactions and transitions
- **Customization Options**: UserCSS variables to toggle UI elements for a minimal, distraction-free interface
- **Code Highlighting**: Enhanced syntax highlighting for code blocks with Gruvbox colors
- **Accessibility First**: Optimized contrast ratios and font rendering for extended use

## Installation

### Prerequisites

1. Install the [Stylus](https://add0n.com/stylus.html) browser extension:
   - [Chrome/Edge](https://chrome.google.com/webstore/detail/stylus/clngdbkpkpeebahjckkjfobafhncgmne)
   - [Firefox](https://addons.mozilla.org/firefox/addon/styl-us/)

2. Install the theme:
   - [Install from UserStyles.world](https://userstyles.world) (coming soon)
   - Or manually install by copying the CSS file into Stylus

## Customization Options

The theme includes several UserCSS variables you can customize:

| Variable | Description | Default |
|----------|-------------|---------|
| `noLogo` | Hide the Claude logo on the front page | ✅ Enabled |
| `noSideHeader` | Hide the sidebar header for cleaner look | ✅ Enabled |
| `newfont` | Choose your preferred text font | Geist Sans |
| `headfont` | Choose your preferred heading font | Inherit |
| `LoadWebFont` | Load custom fonts from web | ❌ Disabled |

## Color Palette

The theme uses the authentic Gruvbox dark color scheme:

### Backgrounds
- `--bg-dark`: #282828 (Primary background)
- `--bg-dark-new`: #1F1E1D (Secondary background)
- `--bg-def-dark`: #171718 (Sidebar background)

### Text Colors
- `--text-white`: #f9f5d7 (Primary text)
- `--text-offwhite`: #fbf1c7 (Secondary text)
- `--text--faded`: #d5c4a1 (Muted text)
- `--text--veryfade`: #928374 (Subtle text)

### Accent Colors
- `--faded-red`: #fb4934 (Headings, errors)
- `--faded-green`: #b8bb26 (Success, links)
- `--faded-blue`: #83a598 (Headings h2-h3)
- `--faded-yellow`: #fabd2f (Warnings)
- `--faded-aqua`: #8ec07c (Inline code)
- `--faded-purple`: #d3869b (Keywords)
- `--faded-orange`: #fe8019 (Secondary accents)

## Key UI Elements Styled

- **Query Bar**: Rounded search input with Gruvbox borders
- **Sidebar**: Dark sidebar with improved contrast
- **Chat History**: Styled conversation list with hover effects
- **Model Selector**: Pill-style button with smooth transitions
- **Action Buttons**: Consistent pill-button styling throughout
- **Code Blocks**: Enhanced syntax highlighting with Gruvbox colors
- **Citations**: Styled reference buttons with hover animations
- **Text Areas**: Improved typography and focus states

## Development

### Code Conventions

- **Language**: Stylus preprocessor
- **Target Domain**: `claude.ai`
- **Indentation**: 4 spaces
- **Selectors**: Use `!important` on properties for override priority
- **Nesting**: Extensive use of Stylus nesting for pseudo-classes
- **Transitions**: All visual changes should be animated
- **Font Rendering**: Antialiased text with optimized legibility

### Commit Message Format

```
type: subject

Types:
- feat: New feature
- fix: Bug fix
- style: Code style changes
- refactor: Code refactoring
- docs: Documentation changes
```

## Browser Support

- Chrome/Chromium-based browsers (with Stylus extension)
- Firefox (with Stylus extension)

## Credits

- [Gruvbox](https://github.com/morhetz/gruvbox) - The original color scheme by Pavel Pertsev
- [Geist](https://vercel.com/font) - Vercel's Geist font family
- [FontSource](https://fontsource.org/) - Web font hosting

## License

Apache 2.0 License

## Contributing

Contributions are welcome! Please ensure your changes follow the existing code style and conventions documented in this README.

---

**Note**: This theme is specifically designed for [Claude AI](https://claude.ai) and applies to the `@-moz-document domain("claude.ai")` scope.
