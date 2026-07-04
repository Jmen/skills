---
name: commit
description: Use when committing changes to version control
---

# Guidance
  
Use conventional commits prefix
  
After the prefix, the commit message should complete the sentance, "Applying this change will ..."

Do not include this initial sentance in the actual message, as the message should be short and concise

Describe the decision, not just the action: the diff already shows what changed, so the message should carry the intent — the benefit, trade-off, or problem being solved. Compress the "what" and spend the saved space on the "why", often as a trailing "for ..." or "so that ..." clause.

Too literal: "ci: test the production build instead of the dev server" (restates the diff)
Better: "ci: run tests against production build rather than dev hot-reload, for more realistic and faster runs" (adds the motivation)

# Examples

feat: allow user to update profile image, so that they can keep it up to date
ci: ensure integrated code passes unit tests, so that builds are failed on issues
chore: apply latest security updates from dependencies, to keep the solution secure
