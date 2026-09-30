# Setup

This project requires a `config.yaml` file in the project root.
Without it, the application fails to start and logs an error:
"Missing configuration file: config.yaml".

To install dependencies, run `pip install -r requirements.txt`.
The minimum supported Python version is 3.10.

   
## Memory and connections

The app uses a connection pool for database access. If memory usage grows steadily under
sustained traffic and doesn't release after requests complete, check that connections are
being returned to the pool correctly rather than leaked. The pool size is configured in
config.yaml (default 5 connections) — increasing it does not fix a leak, only masks it
for longer.

## Pagination

List endpoints use offset-based pagination. Page size defaults to 20 items. When
implementing or modifying pagination logic, be careful with loop boundaries — using `<`
instead of `<=` (or vice versa) against the page boundary is a common source of the last
item on a page being silently dropped.
