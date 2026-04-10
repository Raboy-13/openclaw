# TOOLS.md - Local Notes

Skills define _how_ tools work. This file is for _your_ specifics — the stuff that's unique to your setup.

## Team — My Sub-Agents

I work with two sub-agents for coding tasks:

### Claude Code — Coding Agent (primary)
- **Access:** via acpx direct path (`acpx claude prompt -s <session> "<prompt>"`)
- **Use for:** implementing features, fixing bugs, writing tests, committing changes
- **Flow:** I craft the prompt → Claude Code works → I relay results back
- **Sessions:** Named persistent sessions per project (e.g. `oc-claude-cocbot`)

### Code Explorer — Code Analyst
- **Runtime:** `sessions_spawn(agentId: "code-explorer", mode: "run")`
- **Use for:** tracing execution paths, understanding architecture, investigating complex bugs before implementing
- **Flow:** I delegate → Code Explorer analyzes → I share findings with Claude Code for implementation

## Routing

- **Complex coding tasks** → spawn Code Explorer first to analyze, then route to Claude Code
- **All coding tasks** → route to Claude Code via acpx
- **Non-coding tasks** → handle directly (Lovey)

## How I Delegate

1. Raboy describes the task
2. I decide: Code Explorer (analyze first) or direct to Claude Code
3. For complex tasks: Code Explorer analyzes → I synthesize → Claude Code implements
4. For Claude Code: use acpx direct path with named session
5. I relay results back to Raboy
6. I don't just dump output — I synthesize and explain

## acpx Configuration

```bash
ACPX_CMD="C:\Users\daver\AppData\Roaming\npm\node_modules\openclaw\dist\extensions\acpx\node_modules\.bin\acpx.cmd"
```

Named sessions per project:
- CoCBot: `oc-claude-cocbot`

## What Goes Here

Things like:

- Camera names and locations
- SSH hosts and aliases
- Preferred voices for TTS
- Speaker/room names
- Device nicknames
- Anything environment-specific

## Examples

```markdown
### Cameras

- living-room → Main area, 180° wide angle
- front-door → Entrance, motion-triggered

### SSH

- home-server → 192.168.1.100, user: admin

### TTS

- Preferred voice: "Nova" (warm, slightly British)
- Default speaker: Kitchen HomePod
```

## Why Separate?

Skills are shared. Your setup is yours. Keeping them apart means you can update skills without losing your notes, and share skills without leaking your infrastructure.

---

Add whatever helps you do your job. This is your cheat sheet.

## MemPalace — AI Memory System

**Installed:** v3.0.0 (pip: mempalace)  
**Palace path:** C:\Users\daver\.openclaw\workspace\.mempalace\palace  
**Config:** C:\Users\daver\.mempalace\config.json

### Commands
```
mempalace status           Show drawer counts
mempalace search "query"   Semantic search
mempalace mine <dir>       Re-mine a directory
mempalace wake-up          Show L0 + L1 context
```

### Notes
- Uses ChromaDB with ONNX embeddings (all-MiniLM-L6-v2) — fully offline
- 328 drawers indexed from workspace (as of 2026-04-09)
- Rooms: memory (178), skills (140), general (9), state (1)
- People: Raboy; Projects: Code Explorer, Claude, Claude Code
- CLI at: C:\Users\dave\AppData\Roaming\Python\Python313\Scripts\mempalace.exe
