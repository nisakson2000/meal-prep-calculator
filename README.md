# Meal Prep Calculator

A meal prep calculator built for the **Trust The Skinny Chef V2.0** cookbook. Search 154 macro-friendly recipes, select meals, set how many people and servings per person, and get a consolidated shopping list with scaled ingredients.

**[Try it live](https://nisakson2000.github.io/meal-prep-calculator/)**

![image](https://img.shields.io/badge/Recipes-154-e94560?style=for-the-badge)
![image](https://img.shields.io/badge/Categories-3-5ac8fa?style=for-the-badge)
![image](https://img.shields.io/badge/No_Server-Static_HTML-53d769?style=for-the-badge)

---

## Features

- **Recipe Browser** — Browse and search all 154 recipes with food photos across Breakfast, Lunch & Dinner, and Dessert
- **Macro Info** — Every recipe shows calories, protein, fat, and carbs per serving
- **Meal Prep Calculator** — Select any number of recipes, set how many people and servings per person, and calculate everything at once
- **Categorized Shopping List** — Ingredients are combined across recipes and scaled to your exact needs, then grouped into Proteins, Dairy, Produce, Carbs, Spices, Pantry, and Snacks. Weights are shown in both grams and ounces, and a progress bar tracks what you've already grabbed.
- **Per Recipe Breakdown** — See exactly how each recipe scales: what you need vs. the original amounts
- **Total Macros** — Per-serving and total batch macro breakdown for your entire prep, with a stacked bar showing your protein/fat/carb split
- **Suggestions** — Not sure what to prep? Click ✨ Suggestions for curated picks: Surprise Me (with reroll), High Protein, Balanced Macros, Light & Lean, Calorie Dense, plus Breakfast and Dessert specials

## How It Works

1. **Browse** recipes using search, category filters, or click ✨ Suggestions for curated ideas
2. **Click** recipes to select them — a checkmark appears on selected cards
3. **Set** the number of people and servings per person (e.g., 2 people × 6 servings = 12 total)
4. **Hit Calculate** — get your categorized shopping list, per-recipe breakdown, and macro totals

## Tech

Pure static HTML/CSS/JS — no server, no dependencies, no build step. All 154 recipes and their data are embedded directly in `index.html`. Open the file in a browser or host it anywhere.

- Recipe data parsed from the cookbook PDF using [PyMuPDF](https://pymupdf.readthedocs.io/)
- Food photos extracted from the cookbook
- Ingredient quantities parsed and scaled with fraction math (handles "1 1/2 Cup", "Six Slices", "1-2 Garlic Cloves", gram weights, etc.)
- Ingredients with the same name are combined across recipes and grouped by type in the shopping list

## Built With

Built entirely with [Claude Code](https://claude.ai/claude-code).

---

*Based on the [Trust The Skinny Chef](https://www.youtube.com/@TrustTheSkinnyChef) V2.0 cookbook — 100+ macro-friendly recipes for weight loss without sacrificing flavor.*
