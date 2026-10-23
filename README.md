# Fuel and Reps

A daily food, macro and workout tracker for two people, with a question-answering feature over the logs and a page that evaluates it.

## What it does

- **Food log and macros:** log meals from a built-in food list, a custom food, or plain text ("two chicken thighs and a banana"). Daily calories, protein, carbs, fat and fiber are shown against targets.
- **Eating budget:** the calorie target comes from estimated daily burn (resting burn plus the day's workout) minus a deficit goal, so rest days have a lower budget than gym days.
- **What to eat next:** suggests foods that best fill the remaining gaps for the day.
- **Workout plan:** a weekday plan for each person, with a How panel per exercise, adjustable interval levels and a burn estimate.
- **Weight:** weigh-in log with a trend line toward a goal weight.
- **Ask my logs:** retrieves the relevant day, weight and target records, then has Claude answer from them and list its sources.
- **Evaluate:** generates up to 50 test questions from the data and scores retrieval and answers separately.

## Files

| Path | Purpose |
|---|---|
| `index.html` | The whole app: markup, styles and script in one file |
| `docs/ROADMAP.md` | The 12-week LLM engineering plan and what this project covers so far |
| `docs/DEPLOY.md` | How the app runs today and what changes if it is hosted elsewhere |

## How it runs

The app was built as a Claude artifact. Saving data uses the artifact database, and the macro estimator and Ask feature use the page's Claude access. Outside Claude, `index.html` still opens and works in memory only, with saving and Claude features switched off. See `docs/DEPLOY.md`.

## Data

Records are stored per person and day in these collections: `days`, `profiles`, `foods` and `evalruns`. The default targets and body stats in `index.html` are examples; edit them under Edit targets.
