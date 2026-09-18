---
name: update-github-info
on:
  schedule: daily
  workflow_dispatch:
permissions:
  contents: read
  issues: read
  pull-requests: read
tools:
  github:
  edit:
  web-fetch:
network:
  allowed:
    - github.blog
    - github.com
safe-outputs:
  create-pull-request:
    draft: true
    reviewers:
      - monalisa
---

# Update GitHub Info

Update the GitHub Info website content for Mona's review.

## Sources and guidance

1. Read `notes/mona-notes.md` before drafting anything.
2. Use the GitHub repository API tools to read repository guidance and relevant reference files. Do not use terminal, CLI, or sandboxed commands for repository guidance or reference-file reading.
3. Use `web-fetch` to read the external public guidance and current source material at:
   - https://github.blog/latest/
   - https://github.blog/changelog/
4. Keep summaries short and practical, and cite the source when an update comes from the GitHub Blog or GitHub Changelog.

## Required change

Update `site/content/github-info.md` with useful, current information based on the sources. Preserve the existing editorial angle and make only focused content changes.

## Review workflow

After updating the file, use the `create-pull-request` safe output to open a draft pull request for Mona to review. Include a concise title and body that summarize the sources consulted and the content changed. Do not write directly to the default branch.
