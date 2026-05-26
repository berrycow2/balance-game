# ⚖️ Balance Scale Simulator

> Interactive physics-based balance scale game with educational value

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE.txt)
[![Version](https://img.shields.io/badge/Version-1.2.0-green.svg)](CHANGELOG.md)
[![Tests](https://img.shields.io/badge/Tests-Passing-brightgreen.svg)](#testing)

## 🎯 Purpose

A scientifically-inspired interactive simulator of classical lever scales with realistic physics. Designed for:
- **Education**: Visualize mass ratios, equilibrium principles, and lever mechanics
- **Entertainment**: Casual puzzle gameplay with drag-and-drop interaction
- **Demonstration**: Showcase adaptive 2D graphics, physics simulation, and mobile-first design

## ✨ Features

### Core Gameplay
- 🖱️ **Drag & Drop**: Mouse and touch support for placing items on left/right pans
- 🌊 **Realistic Physics**: Damped pendulum simulation with proportional tilt response
- 📐 **Adaptive Scaling**: Stack up to 1000+ items with automatic size reduction (min 12%)
- 🔄 **Two Visual Modes**: 
  - `Metals`: 16 unique metallic weights (Copper, Gold, Platinum, etc.) with gradient rendering
  - `Emoji`: 85 nature/everyday objects (🪶 Feather, 🍉 Watermelon, 🐘 Elephant, etc.)

### UI & UX
- 🌐 **Bilingual Interface**: Instant RU/EN toggle with full localization
- 📱 **Mobile Optimized**: Touch-friendly hit areas (≥24px), 2-row tray layout on small screens
- 📜 **Report Modal**: Scroll-style report with item breakdown and balance status
- 🔗 **Share Results**: Native sharing API + clipboard fallback
- ℹ️ **Info Panel**: Game instructions and GitHub link

### Developer Features
- 🧪 **Built-in Test Suite**: 4 automated tests (mode switching, performance, physics, i18n)
- 📊 **Performance Monitor**: Real-time FPS, render time, and item count tracking
- 🐛 **Debug Console**: Structured logging with color-coded entries
- 🚀 **Zero Dependencies**: Pure vanilla JS + Canvas 2D, single-file architecture

## 🚀 Quick Start

### Option 1: Web Deployment
1. Save `index.html` to your web server
2. Ensure UTF-8 encoding and `text/html` content-type
3. Open in browser: `https://your-domain.com/balance/`

### Option 2: GitHub Pages
```bash
# Clone and deploy
git clone https://github.com/berrycow2/balance-game.git
cd balance-game
# Enable GitHub Pages in repo settings → Pages → Source: main branch