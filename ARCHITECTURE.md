# 🏗 Архитектура проекта

## Структура единого файла `index.html`
Проект реализован в single-file формате. Логически разделен на 5 слоев:

| Слой | Ответственность | Ключевые функции/переменные |
|------|----------------|-----------------------------|
| **1. Config & Data** | Конфигурация физики, пулы данных, размеры | `WEIGHTS`, `METALS`, `OBJECTS`, `weightSizes`, `SPRING_K`, `DAMPING` |
| **2. State** | Текущее состояние симуляции | `beamAngle`, `angularVelocity`, `leftWeights`, `rightWeights`, `dragging`, `pendingCopies`, `particles` |
| **3. Physics Engine** | Расчет равновесия, затухание, обновление позиций | `updatePhysics()`, `animateStackSettle()`, `getPanScale()` |
| **4. Renderer** | Отрисовка Canvas по Z-порядку | `drawBackground()`, `drawStand()`, `drawBeam()`, `drawPan()`, `drawItem()`, `drawParticles()`, `drawBalanceGlow()` |
| **5. Input & UI** | Обработка pointer-событий, hit-test, модальные окна, кнопки | `onPointerDown/Move/Up()`, `hitPan()`, `hitTestTriangles()`, `showReportModal()`, `layoutTray()` |

## 🔄 Цикл рендеринга

resize() → initSession() → loop()
   ↓
updatePhysics() 
   ↓
updatePans() → updateParticles()
   ↓
clear() → drawBackground() → drawStand() → drawBeam() → drawChain() → drawPan() → drawTray() → drawEffects() → requestAnimationFrame(loop)





## 📐 Физическая модель
- Уравнение маятника с затуханием: `angularVelocity += (targetAngle - beamAngle) * SPRING_K`
- Затухание: `angularVelocity *= DAMPING`
- Целевой угол: `target = clamp(diff * ANGLE_PER_KG, -MAX_ANGLE, MAX_ANGLE)`
- Адаптивное масштабирование стопки: `scale = max(0.12, pow(5/count, 0.55))`

## 💾 State Management
- Грузы на весах хранятся как `{ value, rx, ry, targetRy, meta }`
- `rx/ry` — относительные смещения к центру чаши (гарантирует синхронное движение при наклоне)
- `targetRy` используется для плавной анимации "оседания" стопки при снятии груза
- `pendingCopies` управляет таймером респауна (3000ms + анимация появления)