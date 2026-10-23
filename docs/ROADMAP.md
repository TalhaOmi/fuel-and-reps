# Plan

The plan: a 12-week AI engineer roadmap. This app (Fuel and Reps) is the project it is applied to. Month 1 builds one useful LLM app, month 2 makes it reliable, month 3 ships it and shows the work.

## Done

- **Week 1 (partly):** structured JSON output from Claude, used by the macro estimator and by Ask my logs.
- **Week 2:** use case chosen (answering questions about food, workout and weight logs). The Evaluate page generates up to 50 test cases from the data.
- **Week 3 (partly):** one chunk per person per day, plus weight and target records. Filters by person and date. Ranking is BM25 keyword search.
- **Week 4:** retrieval and answer quality are scored separately. Retrieval: hit rate, recall, rank. Answers: accuracy. Each failure gets a label.
- Known failure from Week 4: questions that compare many days, such as "which day had the most protein". Recall is about 0.3 at K=5.

## Next up (before Week 5)

- [ ] Log a week of real food, workouts and weights so the tests run on real data, not the sample diary.
- [ ] Run Evaluate on the real data and write the baseline numbers here.
- [ ] Write a short note on why the many-day questions fail, and fix them or keep them as a known issue.
- [ ] Commit, and push to GitHub.

## Going to do

| Week | Goal |
|---|---|
| 5 | Add embeddings, combine them with BM25, add reranking, and compare against the Week 4 baseline on the same test cases. |
| 6 | Add a useful tool (log a food item by chat), validate inputs, only allow writing to the signed-in person's own log. |
| 7 | Timeouts, one retry, reject bad JSON, cap tool calls per question. |
| 8 | Test prompt injection and reading the other person's log. Turn each failure into a regression test. |
| 9 | Deploy with a small backend. Trace every retrieval, model call and tool call. |
| 10 | Measure quality, speed and cost for each model, with and without caching. |
| 11 | Get feedback from the two users, fix the top failures, write down the trade-offs. |
| 12 | Publish a case study, update the resume, practise interviews, apply. |

Rule: finish one week at a time. Commit the code and add that week's numbers here before moving on.
