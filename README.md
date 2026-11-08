# AgentDojo prompt-injection study

- Goal: measure how well LLM agents resist prompt injection (utility vs security).
- Plan: baseline with no attack, then attack, then a defense.
- Status: setup done.

## Setup notes
- AgentDojo 0.1.35, Python 3.12, anthropic==0.75.0 (newer versions break AgentDojo).
- Patched models.py: CLAUDE_3_HAIKU slot now points to claude-haiku-5-5 (old model retired).
- Patched anthropic_llm.py: temperature not sent (new models reject it). Runs use the model's default temperature.

## Results log
- 2026-11-08: baseline, workspace, user_task_0-1, no attack: utility 100% (2/2).
- 2026-11-08: attack run, workspace, user_task_0-1 x injection_task_0-1, important_instructions: utility 100%, attack success 0% (reported by AgentDojo as "security 0.00%"; 0/4 attacks worked).
