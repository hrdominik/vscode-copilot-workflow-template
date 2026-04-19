# Database Rules

Apply these rules when writing or modifying database code.

## Queries
- Use parameterized queries — NEVER string-concatenate user input into SQL
- Use the project's ORM/query builder — avoid raw SQL unless necessary
- Always add WHERE clauses to UPDATE and DELETE statements
- Limit SELECT results — no unbounded queries in application code

## Schema & Migrations
- Every schema change requires a migration file
- Migrations must be reversible (include up AND down)
- Add indexes for columns used in WHERE, JOIN, and ORDER BY
- Use appropriate column types and constraints (NOT NULL, UNIQUE, FK)

## Performance
- Avoid N+1 queries — use eager loading / joins
- Add database indexes before optimizing application code
- Use connection pooling — never open connections per request
- Monitor slow queries and add EXPLAIN analysis for complex ones

## Data Safety
- Never delete data permanently in production — use soft deletes
- Back up before running data migrations
- Encrypt sensitive fields (PII, credentials) at rest
- Never log full query results containing user data

## Transactions
- Wrap multi-step operations in transactions
- Keep transactions short — don't hold locks during external calls
- Handle deadlocks with retry logic
