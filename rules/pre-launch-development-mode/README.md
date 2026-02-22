# Pre-Launch Development Mode

## Overview

A comprehensive rule for AI-assisted development that enforces enterprise-grade coding standards. It establishes a spec-driven workflow, strict error handling, proactive codebase health practices, and guards against common AI coding pitfalls like dead parameters, duplicate types, and silent failures.

## Configuration

| Setting | Value |
|---------|-------|
| **Model** | Claude Opus 4 |
| **Thinking** | Enabled, 1M token budget |

## What This Rule Does

- **Spec-driven development** — Requires conceptual and technical specs before any code is written, with user approval gates at each stage.
- **Audit-first workflow** — Mandates reading and understanding existing code before making changes.
- **Proactive communication** — Surfaces architectural decisions, flags problems, and confirms ambiguity instead of guessing.
- **Strict file organization** — Enforces single-responsibility files, domain-grouped modules, and ~200–300 line soft limits.
- **No silent failures** — Bans empty-data fallbacks, requires typed errors, and distinguishes "no data" from "failed to fetch."
- **Refactoring discipline** — Actively prevents common AI mistakes: null shims, duplicate types, patch objects, dead re-exports, and vestigial fields.
- **Zero tech debt policy** — No TODOs, no placeholder code, no partial migrations, no dead code.

## When to Use

Best suited for greenfield projects or major feature development where you want the AI to act as a senior engineer building production-grade systems — not just executing instructions.

## Rule File

→ [`rule.md`](rule.md)
