# Running and deploying

## Today

The app is a single `index.html`. Inside Claude it gets two things from the page runtime:

- a shared document database, used for logs, targets, weights, custom foods and evaluation runs
- access to Claude, used by the "Describe it" macro estimator and by Ask my logs

## Hosting it elsewhere (for example GitHub Pages)

The page will load and the calculators, plan and test-case generator work. Without the Claude runtime:

- nothing is saved after you close the page
- "Describe it" and Ask my logs cannot call Claude
- "Run retrieval only" on the Evaluate page still works with the sample diary

## What a real deployment needs (Weeks 9 and 10)

1. A small backend that stores records in a database.
2. A server-side call to a model API, with the API key kept on the server and never in `index.html`.
3. Sign-in so each person can only read and write their own log.
4. Logging of every retrieval, model call and tool call.

Do not put API keys, passwords or tokens in this repository.

## Before making the repository public

`index.html` contains example body stats (weights, heights, ages) and calorie targets in the defaults near the top of the script. Replace them with neutral values if you do not want them public.
