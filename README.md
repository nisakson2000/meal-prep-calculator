# Meal Prep Calculator

A self-contained recipe and meal-prep app for the **Trust The Skinny Chef V2.0** cookbook. 154 macro-friendly recipes with full step-by-step instructions, smart shopping lists, and personalized suggestions that learn what you cook.

**[Try it live](https://nisakson2000.github.io/meal-prep-calculator/)**

![image](https://img.shields.io/badge/Recipes-154-e94560?style=for-the-badge)
![image](https://img.shields.io/badge/Categories-3-5ac8fa?style=for-the-badge)
![image](https://img.shields.io/badge/No_Server-Static_HTML-53d769?style=for-the-badge)
![image](https://img.shields.io/badge/Privacy-Local_Only-ffcc00?style=for-the-badge)

---

## What it does

- **Read recipes like a cookbook.** Click any recipe to open a full-screen detail view with the photo, macros, ingredient list, and numbered step-by-step instructions.
- **Build a shopping list automatically.** Select recipes, set people × servings, and get a categorized list with weights in both grams and ounces, scaled exactly.
- **Track and personalize.** Mark recipes loved, disliked, or cooked. Suggestions adapt to what you actually make.

---

## Features

### Recipe browser

- All 154 recipes across Breakfast, Lunch & Dinner, and Dessert
- Full-text search and one-tap category filters
- Each card shows calories, protein, fat, carbs, and serving count

### Recipe detail view

Click any card to open the full detail:

- Photo, category, name, macros, and serving info
- Original ingredient list
- Numbered step-by-step instructions, reconstructed cleanly from the cookbook
- Action row to **add to plan**, **love** (👍), **dislike** (👎), or **mark cooked** (✓)
- Deep-linkable via `#recipe/<n>` — share or bookmark a recipe directly
- Keyboard navigation: <kbd>Esc</kbd> closes, <kbd>←</kbd> / <kbd>→</kbd> cycles through your current filter
- Screen stays awake while you cook (Wake Lock API)
- <kbd>Ctrl</kbd>+<kbd>P</kbd> / <kbd>⌘</kbd>+<kbd>P</kbd> prints a clean recipe page

### Meal planning & shopping list

- Combines duplicate ingredients across selected recipes and scales to your exact target
- Categorized into Proteins, Dairy & Eggs, Produce, Grains & Carbs, Spices, Pantry, and Snacks
- Weights shown in both grams and ounces, with proper unit pluralization (`12 Cans · 4082g / 144 oz`)
- Per-recipe breakdown shows scaled vs. original quantities
- Total batch macros and per-serving stacked breakdown
- Built-in checkbox tracker for shopping in-store

### Personalized suggestions

Click ✨ **Suggestions** to see curated sections that adapt as you use the app:

- **🌟 For You** — recipes ranked by category affinity and macro proximity to ones you've loved
- **🍳 Recently Cooked** — quick-access chip strip of your last 10 cooked recipes
- **🎯 Surprise Me** — random shuffle with a reroll button
- **💪 High Protein**, **⚖️ Balanced Macros**, **🍃 Light & Lean**, **🔥 Calorie Dense**
- **☀️ Breakfast Picks** and **🍰 Dessert Picks**
- Disliked recipes are automatically excluded from every suggestion section

When you haven't loved or cooked anything yet, you get the original random sections — no cold-start surprises.

### Cross-device sync

The ⚙ settings menu (next to Suggestions) lets you:

- **Export** preferences to a JSON file
- **Import** them on another device or browser
- **Reset** all preferences with confirmation

---

## How to use it

1. Browse the recipe grid, search by name, or click ✨ Suggestions
2. Click a recipe to open the detail view
3. Use the action bar icons on each card to mark loved (👍), disliked (👎), or cooked (✓)
4. Tap the **+** icon on a card (or **Add to Plan** inside the detail view) to add it to your meal prep
5. Set People × Servings/Person in the right panel
6. Hit **Calculate** to get your shopping list, per-recipe breakdown, and macro totals

---

## Privacy

The app is fully client-side. No server, no account, no telemetry, no cookies. Your love / dislike / cooked marks and shopping selections live in your own browser's `localStorage` and are private to that device. Use **Export / Import** in the settings menu to move them between browsers.

The only external request the page makes is to Google Fonts for typography.

---

## Tech

Pure static HTML / CSS / JS in a single file (`site/index.html`). No server, no dependencies, no build step. All 154 recipes — names, macros, ingredients, instructions, and category — ship in the page itself; photos sit alongside as `images/page_<n>.jpg`.

- **Recipe data** parsed from the cookbook PDF using [PyMuPDF](https://pymupdf.readthedocs.io/) (`parse_cookbook.py`). Each PyMuPDF text block in the instructions section maps to one logical step; whitespace-aware joining repairs PDF column wraps so `"an" + "d whisk"` becomes `"and whisk"` and `"15-2" + "0 minutes"` becomes `"15-20 minutes"`
- **Quantity parsing** handles fractions (`1 1/2 Cup`), ranges (`1-2 Garlic Cloves`), text numbers (`Six Slices`), and weight tags (`(454g)`, `(12oz)`)
- **Personalization** via `localStorage`, keyed by recipe name (durable across recipe regenerations)
- **Modal UX** uses the History API for deep-linking, the Wake Lock API to keep the screen on while cooking, and a `@media print` stylesheet for paper

---

## Built with

Built entirely with [Claude Code](https://claude.ai/claude-code).

---

*Based on the [Trust The Skinny Chef](https://www.youtube.com/@TrustTheSkinnyChef) V2.0 cookbook — 100+ macro-friendly recipes for weight loss without sacrificing flavor.*
