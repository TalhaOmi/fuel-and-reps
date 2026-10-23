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
| `docs/ROADMAP.md` | The plan: what is done, what is next, what is going to be done |

## Data

Records are stored per person and day in these collections: `days`, `profiles`, `foods` and `evalruns`. The default targets and body stats in `index.html` are examples; edit them under Edit targets.
