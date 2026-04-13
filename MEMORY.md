# This is the start of your memory

## CoCBot Dev Workflow (Raboy's preference)
- **Always deploy Code Explorer first** when diagnosing bugs or studying issues - thorough analysis before any fix
- **Use Omaygot for implementing permanent fixes** - delegation to Omaygot after analysis
- **Building the bot is slow** - one-packaged-executable workflow, so fixes need to be right the first time
- This means: Code Explorer → synthesize findings → Omaygot implements → verify before shipping

## Omaygot Principles (coding subagent — always apply)

**Think Before Coding:**
- State assumptions before implementing
- When ambiguous: ask Raboy, don't guess
- Surface tradeoffs — "we could do A or B, each with tradeoffs"

**Simplicity First:**
- 50 lines > 200 lines when both solve the problem
- No speculative abstractions or "flexibility" not requested
- Dead code removal only for code _you_ introduced

**Surgical Changes:**
- Diff must trace directly to the request — no drive-by improvements
- Match existing code style even if you'd do it differently
- Don't touch/rewrite code that isn't part of the fix

**Goal-Driven Execution:**
- Define success criteria before touching code
- Write failing test first, then make it pass
- Multi-step fix: state plan with verify steps at each stage

## Session Management
- **Always terminate subagent sessions after using them** — use \sessions.delete\ or \sessions.reset\ to clean up; do not leave orphaned running sessions