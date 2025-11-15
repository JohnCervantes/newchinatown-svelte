# New China Town - Svelte Refactor

A modern Svelte + Vite refactor of the [New China Town](https://www.newchinatown.net/) restaurant website. This project demonstrates a contemporary, responsive approach to the original site while maintaining all core functionality and user experience.

## Project Overview

New China Town is a beloved Chinese restaurant located in Birmingham, AL. This refactor modernizes their online presence with a fast, responsive, and maintainable web application built with current front-end technologies.

**Original Site:** https://www.newchinatown.net/  

## Tech Stack

### Frontend
- **[Svelte](https://svelte.dev/)** - A cybernetically enhanced web app framework with reactivity built-in
- **[Tailwind CSS](https://tailwindcss.com/)** - A utility-first CSS framework for rapid UI development
- **[Vite](https://vitejs.dev/)** - Next-generation frontend build tool for faster development and optimized builds

### Build & Development
- **Node.js** - JavaScript runtime
- **npm** - Package manager
- **Hot Module Replacement (HMR)** - Instant feedback during development

## Project Structure

```
src/
├── App.svelte           # Main application component
├── main.js             # Application entry point
├── app.css             # Global styles
├── assets/             # Images and static assets
└── lib/                # Reusable components
    ├── Header.svelte       # Navigation and top section
    ├── Main.svelte         # Hero carousel and featured content
    ├── Footer.svelte       # Footer with location and hours
    ├── Testimonial.svelte  # Customer testimonials section
    └── Counter.svelte      # Demo component
```

## Features

- **Fast Performance** - Built with Vite for optimized bundle sizes
- **Component-Based** - Modular Svelte components for maintainability
- **Modern UX** - Improved user experience from the original site

## Getting Started

### Prerequisites
- Node.js (v18 or higher)
- npm or yarn

### Installation

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm build

# Preview production build
npm run preview
```

The development server will typically run at `http://localhost:5173`

## Development

This project uses Vite's HMR for instant feedback during development. Changes to components, styles, and layouts are reflected in the browser immediately.

### Key Dependencies
- `@sveltejs/vite-plugin-svelte@^6.2.1` - Svelte support for Vite
- `tailwindcss@^4.1.17` - Utility CSS framework
- `svelte@^5.43.5` - Svelte framework
- `vite@^7.2.2` - Build tool

## Recommended IDE Setup

[VS Code](https://code.visualstudio.com/) + [Svelte Extension](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode).

[VS Code](https://code.visualstudio.com/) + [Svelte Extension](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode).

The `.vscode/extensions.json` file will prompt you to install the recommended Svelte extension on first open.

## License

This refactor project respects the original New China Town business and is created as a modernization exercise.
