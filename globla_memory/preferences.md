When generating git commit messages for this repository, follow these rules strictly.

### Commit Message Standard

- Always use Conventional Commits.
- Use `type(scope): summary` when a scope is useful.
- Use `type: summary` when no scope is needed.
- Only use these types: `feat`, `fix`, `docs`, `refactor`, `test`, `chore`, `build`, `ci`.

### Style

- Write the summary in the imperative mood.
- Keep the summary lowercase unless a proper noun requires capitalization.
- Keep the subject short and direct.

### Decision Rules

- If a change spans multiple categories, choose the type that is most visible to the user or most significantly changes system behavior.
- If a refactor also fixes a bug, use `fix`.
- If a feature also includes documentation, use `feat`.
- If the intent is ambiguous, infer the best Conventional Commit type from the actual diff instead of asking for clarification.

### Examples

- `fix(auth): prevent stale session redirect loop`
- `feat(factory): add csr signing status stream`
- `docs: update local run instructions`