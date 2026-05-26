
---

## 📁 ФАЙЛ 8: `CHALLENGES.md` (Complex Problems Solved)

```markdown
# Challenges & Solutions

This document details the complex technical problems encountered during development and how they were resolved.

## 🐛 Challenge 1: Item Overlay on Mode Switch

### Problem
When switching between Metals and Emoji modes, visual artifacts appeared: emoji rendered on top of metal gradients (or vice versa), creating a "ghost overlay" effect.

### Root Cause
The `activeItems` and `trayItems` arrays were being repopulated without clearing previous references. Since JavaScript objects are passed by reference, old rendering data persisted in memory.

### Solution
```javascript
// In initSession():
activeItems = [];  // Explicitly clear before repopulating
trayItems = [];
// Then populate with fresh objects from selected mode pool