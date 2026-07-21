# Public fork boundary

This is a public personal fork used to track upstream changes and maintain generic, reusable skill modifications. It is not a project workspace or a storage location for private context.

## Privacy

- Never add captures, private specifications, conversations, local logs, credentials, tokens, personal data, or machine-specific paths.
- Do not copy content from a private consumer repository merely to make a skill example concrete. Use synthetic, minimal examples.
- Keep `.local/`, `.private/`, and environment files untracked.
- Before every commit, review the staged file list and diff, then run `node scripts/check-fork-privacy.mjs`.
- A passing scanner is only a safety net; the staged diff remains the authority.

## Upstream relationship

- `origin` is the personal public fork; `upstream` is the original Matt Pocock repository.
- The default purpose is private consumption of public, generic modifications, not contribution upstream.
- Do not open or prepare an upstream pull request unless the user explicitly asks in that task.
- Review upstream-to-fork changes before merging, then let each consumer repository review its installed projection separately.
