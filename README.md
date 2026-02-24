# Weekly Meal Planner

## Overview

**weekly-meal-planner** is a AI agent skill that generates a personalized 7-day meal plan tailored to your household size, food preferences, and dietary restrictions. It produces:

- Breakfast, Lunch, Dinner, and two Snacks per day
- Consolidated shopping list
- Ingredient substitutions for hard-to-find items
- Optimization to reduce food waste

The skill supports **Vegetarian** and **Non-Vegetarian** diets and automatically scales portions according to the number of people.

---

## Features

- Personalized weekly meal plan for 7 days
- Supports dietary restrictions (gluten-free, dairy-free, low-carb, etc.)
- Scales quantities for 1 or more people
- Minimizes food waste by reusing ingredients across meals
- Easy-to-prepare recipes (≤ 30–40 min)
- Consolidated shopping list organized by category
- Suggestions for affordable and seasonal ingredient substitutes

---

## Usage

Use this skill when you want to:

- Create a weekly meal plan
- Generate a household diet schedule
- Build a shopping list based on food preferences (Veg / Non-Veg)
- Personalize meals based on dietary restrictions

---

# Instructions for Use

1. Make sure you have Node.js and npm installed on your system (required for using npx).

2. Install this skill using one of the following methods:
   - Using the [`Skills CLI`](https://skills.sh/):
     ```bash
     npx skills add https://github.com/tejasashinde/weekly-meal-planner
     ```
   - OR manually:
     - Clone the repository.
     - Place the `weekly-meal-planner` folder inside the `skills` directory (e.g., `.claude/skills`).

3. Trigger the skill using:
   ```bash
   make a weekly meal plan for me
   ```
   and follow the instructions.

---

## License

This project is licensed under the **Apache License 2.0**. See the [LICENSE](LICENSE) file for details.
