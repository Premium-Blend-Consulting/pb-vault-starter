# Sprinklr ruleset naming convention

Apply across all PB-managed accounts.

## Format

`[CLIENT_PREFIX]-[FUNCTION]-[QUALIFIER]-[VERSION]`

## Examples

- `SBX-LISTENING-LOYALTY-v3` — Starbucks listening rules scoped to the loyalty program, version 3
- `ATT-CRISIS-NSFW-v2` — AT&T crisis response rules for NSFW content, version 2
- `WAG-PUBLISHING-APPROVAL-v1` — Walgreens publishing approval workflow, version 1

## Rules

- Always use the client prefix from `wiki/clients/[client]/CONTEXT.md`
- Bump version on any logic change, even minor
- Never delete a ruleset — clone, modify, deprecate the old one
