# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

### Frontend Development
- `pnpm dev` - Start Vite development server for web version
- `pnpm build` - Build the Vue frontend (includes TypeScript type checking)
- `pnpm preview` - Preview the built frontend

### Tauri Desktop App
- `pnpm run "tauri dev"` - Start Tauri development with hot reload
- `pnpm run "tauri build"` - Build production desktop app for all platforms
- `pnpm run "tauri debug"` - Build debug version of desktop app
- `pnpm run "tauri preview"` - Preview the built Tauri app

### Documentation
- `pnpm run "docs:dev"` - Start VitePress documentation development server
- `pnpm run "docs:build"` - Build documentation site
- `pnpm run "docs:preview"` - Preview built documentation

### Utilities
- `pnpm run icon` - Generate app icons using Tauri icon generation
- `pnpm run "update tauri"` - Update Tauri dependencies in src-tauri/Cargo.toml
- `pnpm run "rm:cache"` - Clear Cargo package cache

## Project Architecture

### Core Structure
PakePlus is a desktop app packaging tool built with:
- **Frontend**: Vue 3 + TypeScript + Element Plus UI
- **Desktop Runtime**: Tauri v2 (Rust-based, lightweight alternative to Electron)
- **Documentation**: VitePress for comprehensive multilingual docs
- **Packaging**: Supports web-to-desktop conversion for any website/web app

### Key Directories
- `src/` - Vue 3 frontend application
- `src-tauri/` - Rust backend for desktop functionality
- `docs/` - VitePress documentation (English, Chinese, Japanese)
- `scripts/` - Build scripts and utilities
- `pwa/` - PWA-specific assets

### Frontend Architecture
- **Pages**: `src/pages/` - Main application views (home, edit, phone, etc.)
- **Components**: `src/components/` - Reusable Vue components
- **APIs**: `src/apis/` - HTTP client and API integration
- **Store**: `src/store/` - Pinia state management
- **Internationalization**: `src/lang/` - Multi-language support (EN, CN, JP, KR)

### Tauri Integration
- `src-tauri/src/command/` - Rust commands exposed to frontend
- `src-tauri/src/utils/` - Rust utility functions
- Desktop APIs accessible via `@tauri-apps/api` in frontend
- Cross-platform builds for Windows, macOS, Linux

### Development Notes
- Uses PNPM as package manager
- TypeScript strict mode enabled
- Element Plus auto-import configured
- Vite build with manual chunking for optimal loading
- Development server runs on port 1420 for Tauri compatibility

### App Functionality
PakePlus allows users to:
1. Convert any website into a desktop/mobile app
2. Package Vue/React projects as standalone apps
3. Support local packaging without GitHub dependencies
4. Inject custom JavaScript for app customization
5. Generate multi-platform builds (Windows, macOS, Linux, Android, iOS)