# Pre-Launch Development Mode

You are working on a pre-launch application. Every change must be production-quality from day one. There is no "we'll fix it later."

## Before Writing Any Code

1. **Audit first, implement second.** Before modifying any file or system, read and understand the current state of every file you're about to touch. Trace the full dependency chain. Identify what exists, what's broken, what's redundant, and what's missing.
2. **State your understanding.** Before implementing, briefly explain: what currently exists, what needs to change, and why. If you're unsure about something, say so and investigate — don't assume.

## Implementation Standards

- **No path of least resistance.** Do not pick the quick hack over the correct architecture. If something should be refactored to be done right, refactor it.
- **Zero tech debt.** Every line of code you write should be something you'd be comfortable shipping to production and maintaining for years. No TODOs, no "temporary" workarounds, no shortcuts.
- **Zero legacy code.** If you're replacing a system, fully remove the old one. No dead code, no unused imports, no orphaned files, no commented-out blocks left behind.
- **Zero fallbacks to broken patterns.** Do not silently fall back to placeholder data, mock responses, hardcoded values, or stub implementations. If something isn't working, surface the error — don't mask it.
- **Complete implementations only.** Do not leave functions half-built, endpoints partially wired, or features missing error handling. Every piece of code should be fully functional when you're done.

## Code Quality

- Proper error handling on every async operation and external call — no swallowed errors.
- Type safety everywhere. No `any` types, no implicit type coercion, no unvalidated inputs.
- Environment variables and configuration handled correctly — no hardcoded secrets, URLs, or magic strings.
- Database queries should be efficient, properly indexed, and use transactions where appropriate.
- API responses should have consistent schemas, proper status codes, and meaningful error messages.

## When Modifying Existing Code

- Read the full file before editing, not just the function you're changing.
- Check for other references to what you're modifying — don't break callers.
- If you find existing tech debt or broken patterns while working, fix them. Don't build on top of a broken foundation.
- Clean up after yourself: remove unused imports, dead functions, and stale comments.

## What I Never Want to See

- `// TODO: implement later`
- `console.log` used as error handling
- Catch blocks that swallow errors silently
- Mock data or placeholder responses in production code paths
- Multiple implementations of the same thing because the old one wasn't removed
- "It works on my machine" code that skips proper environment configuration
- Partial migrations where half the code uses the old pattern and half uses the new one
