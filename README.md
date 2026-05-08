# neva-ai

`neva-ai` is an AI-first CLI built in Nevalang.

## Scope

- Keep AI/LLM dependencies out of the main `nevalang/neva` Go module.
- Implement the orchestration flow in Nevalang first.
- Add runtime/stdlib capabilities incrementally behind explicit `#extern` contracts.

## CLI modes

- `chat` mode (default when no command): starts an interactive session.
- `run` mode: executes one tool call path.

## Input model

- `command` and `flags` describe structured intent.
- `prompt` is a string parameter (optional, arbitrary text).
- final user message = typed command rendering + optional free-form prompt.

## Current status

This repository currently contains a contract-first skeleton:

- Nevalang flow definition in [flows/main.neva](./flows/main.neva)
- Architecture notes in [docs/architecture.md](./docs/architecture.md)
- Missing runtime hooks documented as `#extern` contracts.
