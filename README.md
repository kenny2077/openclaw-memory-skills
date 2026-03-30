# OpenClaw Memory Skills

This package contains two improved OpenClaw skills:

- `durable_memory_writer` — decides what should be stored in long-term memory versus daily notes
- `import_external_memory` — converts pasted memory from other assistants into clean OpenClaw memory

## Install

Copy these folders into your workspace skills directory:

```bash
mkdir -p ~/.openclaw/workspace/skills
cp -R durable_memory_writer ~/.openclaw/workspace/skills/
cp -R import_external_memory ~/.openclaw/workspace/skills/
openclaw gateway restart
openclaw skills list
```

## Test prompts

### durable_memory_writer

```text
Remember this: I prefer concise answers first, then more detail if I ask.
```

```text
Remember this: I want 3 coding solution tiers from brute force to final optimization.
```

### import_external_memory

```text
Import this memory from my other assistant:
- I am a CS student.
- I prefer plain explanations.
- I am building OpenClaw memory tools.
- Keep examples practical.
```

## Notes

OpenClaw stores durable memory in `MEMORY.md` and recent notes in `memory/YYYY-MM-DD.md`.
