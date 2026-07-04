---
name: pr-description
description: Use when creating a Pull Request
---

# Steps

- List the files changed with links to where they are in the repo
- Break the file list down into sections
- Every changed file appears in exactly one section
- Order the sections so that they build understanding of the change sequentially
- Output in raw markdown compatible with GitHub surrounded in a code block

# Reference

- Use bullet point lists instead of paragraphs of text
- Underscores in file paths need to be escaped, otherwise they will be styled as bold text

## Template

<Title> What problem does this change solve?

<Description> What is the wider context of this change

<Section 1> Simplest fundamental part of change that everything builds from

<File1>
<File2>
<File3>

<Section 2> Next part of change which builds from the previous section

<File4>
<File5>
<File6>

<DeploymentRisk>

low - risks are unlikely to happen or low impact
medium - risks are either likely to happen, or high impact
high - risks are high impact and likely to happen