# 12-week plan and project status

The plan builds one LLM app over three months: build it, make it reliable, then ship it and show the work. This project is the app. Status is marked honestly.

## Month 1: Build one useful LLM app

| Week | Goal | Status here |
|---|---|---|
| 1 | Tokens and context windows, structured outputs, tool calling, connect an LLM to a backend | Partial. Structured JSON output is used by the macro estimator and by Ask my logs. No tool calling yet. There is no own backend: calls go through the page runtime. |
| 2 | Focused use case with real data, 30 to 50 test cases | Done. Use case is answering questions about food, workout and weight logs. The Evaluate page generates up to 50 cases. Real logs are still few, so the sample diary is used for now. |
| 3 | RAG with chunking, embeddings, vector search and metadata filters | Partial. One chunk per person per day, plus weight and target records. Person and date filters work. Ranking is BM25 keyword search. No embeddings or vector search yet. |
| 4 | Evaluate retrieval and answer quality separately and find failures | Done. Evaluate page reports hit rate, recall and rank for retrieval, accuracy for answers, and labels each failure. Known failure: questions that need many days at once, such as which day had the most protein. |

## Month 2: Make it reliable

| Week | Goal | Next step in this project |
|---|---|---|
| 5 | Test hybrid search and reranking against the baseline | Keep the BM25 numbers from Week 4 as the baseline. Add embeddings, combine with BM25, rerank, and compare on the same test cases. |
| 6 | Add a useful tool, validate inputs, enforce permissions | Let the assistant log a food item as a tool call. Validate quantities and foods, and only allow writing to the signed-in person's own log. |
| 7 | Handle retries, timeouts, invalid outputs, limit tool calls | Add timeouts and one retry, reject bad JSON, cap tool calls per question. |
| 8 | Test prompt injection and unauthorized access, turn failures into regression tests | Put hostile text in a food name or note and check the assistant ignores it. Try reading the other person's log. Save each failure as a test case. |

## Month 3: Ship it and prove your skills

| Week | Goal | Next step in this project |
|---|---|---|
| 9 | Deploy, add tracing for retrieval, model calls and tools | Move the app and a small backend to a host you control. Log each retrieval, model call and tool call. |
| 10 | Measure quality, latency and cost, test model choices and caching | Record accuracy, time and cost per question for each model and with caching on and off. |
| 11 | Collect user feedback, fix failures, document trade-offs | Ask the two users to flag wrong answers. Fix the top failures. Write down what was traded off. |
| 12 | Publish a case study, update resume, practice interviews, apply | Write the case study from the Week 4 to 10 results. |

## Working rule

Finish one week at a time. Before moving on, commit the code and add the week's numbers to this file.
