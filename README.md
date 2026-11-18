# CalorTracker Food Nutrition Dataset (USDA-derived)

461 common foods with calories, macronutrients, vitamins and minerals per 100 g, and 1335 household portions, taken from
USDA FoodData Central and keyed by FDC id and by the slug of each food's page on CalorTracker.

Version: 2026-11-18 (the foods live on calortracker.com that day, in 19 categories).
Browse the same foods at https://calortracker.com/nutrition.

## License

CC0 1.0 Universal, the same public-domain dedication USDA applies to FoodData Central. Use it for anything, with no permission needed.
The license asks for no credit. USDA requests that FoodData Central be cited as below, and a link back to CalorTracker is welcome.

## Source and credit

All values come from USDA FoodData Central (https://fdc.nal.usda.gov/): U.S. Department of Agriculture, Agricultural Research
Service. FoodData Central, fdc.nal.usda.gov. FDC releases used: FoodData Central FNDDS (Survey Foods) 2024-10-31, FoodData Central Foundation Foods 2026-04-30, FoodData Central SR Legacy 2018-04. Each row carries its
`fdc_id`, `usda_description`, `usda_release` and a link to its FDC page, so every figure can be checked at the source.

CalorTracker adds the page slug, a category, the food name and the order of portions. It does not adjust any nutrient value.

## Files

| File | What it holds |
|---|---|
| `foods.csv` | One row per food: identity, USDA source and 31 nutrients per 100 g. |
| `portions.csv` | USDA household portions per food (`slug`, `position`, `label`, `grams`). |
| `foods.json` | The same foods as JSON, nutrients nested in `per100g`, portions as an array. |
| `datapackage.json` | A Frictionless Data manifest: license, sources, field definitions, byte size and SHA-256 of each file. |

## Reading the columns

- Nutrient columns end in their unit: `protein_g`, `sodium_mg`, `vitamin_d_ug` (micrograms). All are per 100 g of the food as USDA lists it.
- An empty cell (null in JSON) means USDA reported no value. It does not mean zero.
- `energy_kcal` is USDA's energy figure; `energy_source` says whether it is the measured Energy value or an Atwater estimate.
- `usda_description` says whether the row is raw or cooked, with skin or without. The CalorTracker `name` is shorter.
- A portion's `grams` is the weight USDA records for that household measure. Portions vary by food and are not standard servings.

## More files

| File | What it holds |
|---|---|
| `LICENSE` | The CC0 1.0 Universal legal text. |
| `CHANGELOG.md` | Foods added and corrections, generated from https://calortracker.com/nutrition/changelog. |
| `dataset-metadata.json` | The Kaggle dataset card. |
| `huggingface/README.md` | The Hugging Face dataset card (this README with YAML front matter). |

## Derived and cleaned by CalorTracker

CalorTracker (https://calortracker.com) is a calorie and nutrition tracker. This dataset is the food reference behind its public nutrition pages.
Each food has a page at `page_url`; the same numbers are available through the free API described at https://calortracker.com/developers.
"Cleaned" means: USDA rows matched to common food names, a raw or cooked row chosen deliberately, URL-safe slugs, one fixed column
per nutrient with its unit in the name, and household portions in grams. Nutrient values are USDA's, unchanged.

## How it was built

Rebuilt by `npx tsx scripts/build-open-dataset.ts` from the food files in the CalorTracker repository (`content/foods`), which are
themselves read from USDA FoodData Central downloads. The build is deterministic: the same food files and the same version date give
byte-identical output, and the `datapackage.json` hashes let you verify a copy. Only foods that are live on calortracker.com on the
version date are included (461 on 2026-11-18); a food that is scheduled or held is never listed.

## Versioning

The version is the date the dataset describes (`2026-11-18`), not the day it was run. Every time CalorTracker adds a wave of
foods or corrects a value, a new version is built and CHANGELOG.md gets a dated entry. Pin a version by its date.

## Citation

> U.S. Department of Agriculture, Agricultural Research Service. FoodData Central. fdc.nal.usda.gov.
>
> CalorTracker Food Nutrition Dataset (USDA-derived), version 2026-11-18. CalorTracker, https://calortracker.com/nutrition. CC0 1.0.

## Not medical advice

These are reference values for foods in general. A particular brand, ripeness or recipe will differ. Nothing here is dietary or medical advice.
