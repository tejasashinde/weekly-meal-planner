---
name: weekly-meal-planner
description: "Use this skill when the user asks to create a weekly meal plan, make a weekly meal plan, generate a weekly diet plan, prepare a household meal schedule, build a shopping list based on food preferences (veg/non-veg). Automatically personalises the weekly plan based on number of people and dietary restrictions."
---

# Weekly Meal Planner

## Purpose

Generates a personalized 7-day meal plan including:

- Breakfast  
- Lunch  
- Dinner  
- Two Snacks per day

The plan:
- Supports vegetarian and non-vegetarian preferences
- Scales automatically based on household size
- Minimizes food waste by reusing ingredients across meals
- Uses fresh, easy-to-prepare ingredients
- Produces a consolidated shopping list
- Suggests substitutions for hard-to-find ingredients

---

## When to use this skill

Use this skill when the user asks to 'create a weekly meal plan','make a weekly meal plan','generate a weekly diet plan','prepare a household meal schedule','build a shopping list based on food preferences (veg/non-veg)'.

## REQUIRED INPUTS

Before generating the meal plan, you MUST ensure the following inputs are collected and confirmed.
If any required input is missing, you MUST explicitly ask the user before proceeding.

---

### 1. Number of People

- Defines portion sizes and shopping quantities.
- If the user does NOT provide this value:
  - Ask:  
    "How many people should this meal plan serve?"
  - If none are provided, assume `1`.

- Value must be a positive integer. If user gives something else, assume `1`.

---

### 2. Food Preference

- Must be one of:
  - Vegetarian (Veg)
  - Non-Vegetarian (Non-Veg)

- If not specified, you MUST ask:  
  "Do you prefer Vegetarian or Non-Vegetarian meals?"

- Do NOT assume a default food preference.

---

### 3. Dietary Restrictions (If Any)

- Ask the user:  
  "Do you have any dietary restrictions or allergies? (Default is No)"

- If none are provided, assume `No dietary restrictions`.

- Examples include (but are not limited to):
  - No dairy
  - Gluten-free
  - Low-carb
  - Diabetic-friendly
  - Jain diet
  - Nut allergy

- The meal plan MUST strictly respect any stated restriction.

---

### Validation Rules

- Do NOT generate the meal plan until all required inputs are confirmed or defaulted properly.
- Do NOT ignore dietary restrictions.
- Portion sizes and shopping list quantities MUST scale according to the number of people.

---

## Execution Steps

### Step 1: Validate & Confirm Inputs (Mandatory Gate)

Before generating the meal plan, you MUST ensure all required inputs are confirmed.

Required:
- Number of People (default = 1 only if user does not respond)
- Food Preference (Vegetarian / Non-Vegetarian) -> NO default allowed
- Dietary Restrictions (default = None if not provided)

Rules:
- If any required input is missing, you MUST ask the user.
- Do NOT generate the meal plan until inputs are fully confirmed or defaulted properly.
- Do NOT assume Vegetarian or Non-Vegetarian.
- Portion sizes and shopping quantities MUST scale based on number of people.
- Dietary restrictions MUST override all meal decisions.

---

### Step 2: Generate Weekly Meal Plan

Produce a structured 7-day meal schedule.

For each day:

**Day X**
- Breakfast:
- Snack 1:
- Lunch:
- Snack 2:
- Dinner:

Meal Requirements:
- Balanced macronutrients (protein, carbs, fats, fiber)
- Ingredient overlap across meals to reduce waste
- Use seasonal and accessible ingredients
- Simple preparation (≤ 30–40 minutes preferred)
- Avoid repeating the exact same full meal more than twice per week
- Respect food preference strictly (Veg / Non-Veg)
- Fully comply with dietary restrictions

---

### Step 3: Optimize for Waste Reduction

Design meals intentionally to minimize food waste:

- Reuse vegetables across multiple dishes
- Batch-cook proteins where applicable
- Reuse grains across meals
- Convert leftovers into next-day variations

Examples:
- Roasted vegetables -> Wrap or sandwich filling
- Boiled chickpeas -> Salad + curry
- Grilled chicken -> Rice bowl + sandwich
- Cooked rice -> Stir-fry + side dish

---

### Step 4: Generate Consolidated Shopping List

Organize into clear categories:

- Vegetables
- Fruits
- Grains & Cereals
- Proteins
- Dairy (if applicable)
- Spices & Condiments
- Snacks & Miscellaneous

Rules:
- Scale quantities according to number of people
- Avoid duplicate ingredients
- Combine repeated items into single total quantities
- Align strictly with the weekly plan

---

### Step 5: Suggest Substitutions

For ingredients that may be expensive, seasonal, or difficult to find, provide practical alternatives.

Format:

- Quinoa -> Substitute: Brown rice
- Kale -> Substitute: Spinach
- Greek yogurt -> Substitute: Regular curd

Rules:
- Keep substitutes affordable and widely available
- Ensure substitutes respect dietary restrictions
- Maintain similar nutritional value where possible

---

## OUTPUT FORMAT

You MUST strictly follow the exact structure, formatting, headings, and section order as defined in:

[markdown](`references/OUTPUT-TEMPLATE.md`)

You MUST follow below rules for creating Word document:

1. Convert the Markdown content into a Word document:
`pandoc weekly_meal_plan.md -o weekly_meal_plan.docx`
2. Preserve all formatting: headings, bold, emojis, lists, and indentation.
3. Do NOT modify section titles, heading levels, or order.
4. The final document file MUST be strictly saved as: [word](`weekly_meal_plan.docx`)
5. STRICTLY DO NOT TRY TO OPEN THE GENERATED FILE, instead just respond calmly that file is saved at location and end execution.

---

### STRUCTURE RULES (NON-NEGOTIABLE)

1. Do NOT modify section titles.
2. Do NOT change heading levels.
3. Do NOT change the order of sections.
4. Do NOT add extra sections.
5. Do NOT remove any required section.
6. Do NOT change formatting style (spacing, bullets, separators).
7. All 7 days must be present (Day 1 to Day 7).

The structure must remain IDENTICAL to the template.

---

### CONTENT ADAPTATION RULES (IMPORTANT)

1. Food Preference (Vegetarian / Non-Vegetarian) affects ingredients ONLY.
2. Dietary Restrictions affect ingredients ONLY.
3. Goals (if provided) affect meal composition ONLY.
4. Structure must NEVER change due to preference, restriction, or goal.
5. If a restriction conflicts with a typical ingredient, replace the ingredient — do NOT alter layout.
6. Shopping list quantities MUST scale according to number of people.

---

### ENFORCEMENT RULE

Dietary restrictions, food preference, and goals modify content but never the document structure.

---