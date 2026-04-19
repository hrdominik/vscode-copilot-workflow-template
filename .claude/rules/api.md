# API Rules

Apply these rules when writing or modifying API code.

## Endpoints
- Use RESTful conventions: nouns for resources, HTTP verbs for actions
- Version APIs in the URL path: `/api/v1/resource`
- Return consistent response shapes: `{ data, error, meta }`

## Validation
- Validate ALL input at the API boundary — never trust client data
- Use schema validation (zod, joi, pydantic) — not manual checks
- Return 400 with specific error messages for invalid input

## Security
- Authenticate every endpoint unless explicitly public
- Authorize at the resource level — check ownership, not just login
- Rate limit all public endpoints
- Never expose internal IDs, stack traces, or DB errors to clients

## Error Handling
- Use standard HTTP status codes correctly (don't use 200 for errors)
- Log errors server-side with context (request ID, user, action)
- Return user-friendly error messages, not raw exceptions

## Performance
- Paginate list endpoints — never return unbounded results
- Use appropriate caching headers
- Keep payloads minimal — only return requested fields when possible
