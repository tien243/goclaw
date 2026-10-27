# Review Guidelines

## What failure looks like in this repo
- **It breaks the API contract** — endpoint returns wrong shape, status code, or error format
- **It leaks data** — sensitive fields exposed, auth bypass, missing permission checks
- **It corrupts state** — database writes without validation, race conditions, missing transactions

## What to check
1. Every API endpoint change: verify request/response types match docs
2. Database operations: check for transactions, validation, error handling
3. Auth/permissions: verify middleware is applied on new routes
4. Environment variables: no hardcoded secrets, all new vars documented

## What to skip
- `node_modules/`, `dist/`, `build/`, `.next/`
- Generated files, lock files
- Pure comment/formatting changes

## Evidence required
- Cite exact **file path and line number** for every finding
- Do NOT guess from function names alone

## Nit cap
- Maximum 2 nits per review. Focus on bugs and security.

## Summary format
- Start with: "Found X issues (Y important, Z nits)"
- If nothing to fix, say: "No issues found"
