# Backlog: extern implementations

Priority order for bringing MVP to executable state:

1. `neva_ai_parse_cli`
- parse `chat|run`
- parse `--tool`, `--prompt` (string parameter)
- defaults: no command => `chat`

2. `neva_ai_build_session_input`
- render typed command into normalized text instruction
- append optional arbitrary prompt

3. `neva_ai_command_to_tool_call`
- convert `run` command into direct `ToolCall`

4. `neva_ai_choose_tool`
- invoke LLM with `tools + message`
- return typed `ToolCall`

5. `neva_ai_execute_tool`
- dispatch by tool name
- bridge to future `pkg/cli` runtime adapter

6. `neva_ai_route`
- branch between `Chat` and `Run` modes
- preserve error semantics (`err error` path)
