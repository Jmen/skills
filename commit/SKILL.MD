---
name: commit
description: how to write a git version control commit message
---

# Guidance
  
Use conventional commits
  
The commit message should complete the sentence, "Applying this change will ..."

Do not include this prefix in the actual message, as the message should be short and concise

Describe the decision, not just the action: the diff already shows what changed, so the message should carry the intent — the benefit, trade-off, or problem being solved. Compress the "what" and spend the saved space on the "why", often as a trailing "for ..." or "so that ..." clause.

Too literal: "ci: test the production build instead of the dev server" (restates the diff)
Better: "ci: run tests against production build rather than dev hot-reload, for more realistic and faster runs" (adds the motivation)

# Examples

feat: make the send method more readable
ci: run the unit tests in the pipeline
chore: upgrade to the latest dependency packages
ci: run tests against production build rather than dev hot-reload, for more realistic and faster runs
