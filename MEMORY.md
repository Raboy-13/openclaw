# This is the start of your memory

## CoCBot Dev Workflow (Raboy's preference)
- **Always deploy Code Explorer first** when diagnosing bugs or studying issues — thorough analysis before any fix
- **Use Omaygot for implementing permanent fixes** — delegation to Omaygot after analysis
- **Building the bot is slow** — one-packaged-executable workflow, so fixes need to be right the first time
- This means: Code Explorer ? synthesize findings ? Omaygot implements ? verify before shipping

## Session Management
- **Always terminate subagent sessions after using them** — use `sessions.delete` or `sessions.reset` to clean up; do not leave orphaned running sessions