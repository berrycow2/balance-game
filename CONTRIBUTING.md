# Contributing to Balance Scale Simulator

Thank you for considering contributing to this project! This document provides guidelines for making the process smooth and effective.

## 🤝 How to Contribute

### Reporting Bugs
1. Check the [issue tracker](https://github.com/berrycow2/balance-game/issues) to avoid duplicates
2. Create a new issue with:
   - Clear title and description
   - Steps to reproduce
   - Expected vs actual behavior
   - Device/browser info (if UI-related)
   - Screenshots/console logs if helpful

### Suggesting Enhancements
1. Open an issue with `[Enhancement]` prefix
2. Describe the feature, its value, and potential implementation approach
3. Be open to discussion and iteration

### Code Contributions
1. **Fork** the repository
2. **Create a branch**: `git checkout -b feature/your-feature-name`
3. **Make changes** following existing code style
4. **Test locally**: 
   - Run built-in tests (🧪 button)
   - Verify mobile/desktop behavior
   - Check performance with 50+ items
5. **Commit** with descriptive messages: `feat: add X`, `fix: resolve Y`
6. **Push** and open a **Pull Request**

## 🧪 Development Guidelines

### Code Style
- Use ES6+ syntax (const/let, arrow functions, template literals)
- Prefer functional patterns over class inheritance
- Comment complex logic (physics, rendering optimizations)
- Keep functions focused (<50 lines ideal)

### Performance
- Avoid unnecessary DOM queries in render loop
- Use object pooling for particles if expanding effects
- Profile with `PerfMonitor` before/after changes
- Target: ≥45 FPS with 100 items on mid-range mobile

### Testing
- Add test cases to `Tests` object for new features
- Ensure existing tests still pass
- Document performance impact in PR description

### Localization
- Add new strings to `i18n` object for both `ru` and `en`
- Use `t(key)` helper for all user-facing text
- Test both languages after changes

## 🚫 What We Won't Accept

- External library dependencies (keep zero-dependency architecture)
- Breaking changes to core physics or UX without discussion
- Code that reduces mobile performance below 45 FPS
- Unlocalized user-facing text

## 📬 Getting Help

- Open an issue with `[Question]` prefix
- Check `structure.md` for code architecture details
- Review `LESSONS_LEARNED.md` for common pitfalls

## 🙏 Recognition

Contributors will be credited in:
- `README.md` authors section
- Release notes in `CHANGELOG.md`
- GitHub repository contributors tab

Thank you for helping make this project better! 🎯⚖️