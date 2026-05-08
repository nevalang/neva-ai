# Architecture (MVP)

## Goal

Build `neva-ai` as a separate repo and implement the control plane in Nevalang.

## Pipeline

1. Parse CLI args into typed `Command`.
2. Build normalized user message from command + optional prompt.
3. Load tool definitions.
4. Call LLM with `tools + prompt`.
5. Execute selected tool by calling a typed runtime bridge (`pkg/cli` adapter later).
6. Print result.

## Why contract-first

Nevalang runtime APIs for full LLM/tool-calling are not complete yet.
To keep momentum, MVP uses explicit `#extern` contracts and implements orchestration now.

## Missing capabilities (expected)

- robust CLI parsing (flags, quoting, escaping)
- HTTP client with headers/auth + JSON encode/decode helpers
- tool-call schema marshalling
- interactive chat loop with state/history
- runtime bridge for `pkg/cli` function calls

These are intentionally modeled as explicit extern boundaries in `flows/main.neva`.
