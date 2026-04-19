# Frontend Rules

Apply these rules when writing or modifying frontend code.

## Components
- Keep components small and single-purpose
- Separate data fetching from presentation
- Use the project's existing component patterns — check before creating new ones
- Colocate styles, tests, and types with their components

## State Management
- Keep state as local as possible — lift only when needed
- Avoid duplicating server state in client state
- Use the project's established state management solution
- Derive values instead of storing computed state

## Performance
- Lazy load routes and heavy components
- Memoize expensive computations — but profile first, don't guess
- Avoid unnecessary re-renders — use React.memo / useMemo only where measured
- Optimize images: proper formats, sizes, and lazy loading

## Accessibility
- Use semantic HTML elements (button, nav, main, etc.)
- Add ARIA labels to interactive elements without visible text
- Ensure keyboard navigation works for all interactive elements
- Maintain sufficient color contrast (WCAG AA minimum)

## Security
- Sanitize any user content rendered as HTML
- Never store tokens in localStorage — use httpOnly cookies
- Validate form inputs client-side AND server-side
- Use CSP headers to prevent XSS
