# Changelog

What changed in the CalorTracker Food Nutrition Dataset (USDA-derived), newest first. It is generated from the data changelog at https://calortracker.com/nutrition/changelog, which counts additions
straight from the food files' publish dates. The latest version is 2026-11-18.

## 2026-10-29

- Added 391 foods. Each with calories, protein, carbs, fat, fiber and the USDA nutrient panel per 100 g, plus portions. By category: 56 vegetables, 39 meat and poultry, 36 mixed dishes, 26 fish and seafood, 24 beverages, 24 condiments and sauces, 22 fruits, 22 sweets and desserts, 20 grains and pasta, 19 bread and bakery, 19 eggs and dairy, 17 nuts and seeds, 16 legumes and soy, 14 cheese, 11 alcoholic drinks, 9 snacks, 8 fats and oils, 5 breakfast cereals, 4 herbs and spices.

## 2026-10-22

- Wave 1 matches checked against USDA: Before the 231 wave 1 foods went on the schedule, we checked every USDA match: the right raw or cooked row, a plausible calorie figure, macros that add up, and a realistic first serving. Five needed a correction.
- Corrected French Bread: the first serving was a 139 g slice of a whole loaf; it is now 1 oz (28 g)
- Corrected Whole Wheat Flour: switched to the standard whole-grain wheat flour row (FDC 168893) from the soft pastry-flour row
- Corrected Whole Wheat Pasta (Cooked): switched to the 100% whole-wheat cooked pasta row (FDC 168910) from a 51% whole-wheat blend
- Corrected Turkey Breast (Roasted): switched to skinless roasted breast meat (FDC 171496) from meat and skin
- Corrected Granola: the first serving was 1 cup (122 g); it is now 1 oz (28 g)

## 2026-10-20

- First 70 foods on USDA data: The first 70 food pages were rebuilt from USDA FoodData Central files. Before this, their numbers had been typed by hand. We compared each page with the old values: 18 of the 70 differed by more than 10% in at least one field (kcal, protein, carbs, fat, fiber or sugar), and those now show the USDA figure.
