# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
yarn lint          # Run stylelint on all CSS files
yarn lint:fix      # Auto-fix stylelint issues
yarn format        # Format all files with Prettier
yarn format:check  # Check formatting without writing
```

## Architecture

This is a collection of UserStyle CSS files (`.user.css`) for browser extensions like Stylus. Each file targets a specific website using `@-moz-document domain("...")` blocks.

All styles live in `css/` and follow the UserStyle metadata format:

```css
/* ==UserStyle==
@name           site-name
@namespace      cybergene.dev/userstyles
@version        1.0.0
@description    user style for site-name
@author         cybergene
@updateURL      https://raw.githubusercontent.com/cyber-gene/UserStyles/main/css/site.user.css
==/UserStyle== */
```

## Style Rules

- Stylelint extends `stylelint-config-standard` with `-moz-document` allowed as an at-rule
- Vendor prefixes are permitted (`property-no-vendor-prefix` and `at-rule-no-vendor-prefix` are disabled)
- `no-descending-specificity` is disabled (common in UserStyles)
- Prettier uses 2-space indent, single quotes, semicolons, 80-char print width
- CI runs Prettier check and stylelint on every PR to `main`
