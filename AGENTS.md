# Agent Instructions

## Commit Conventions

Use **Conventional Commits** format:

```
<type>(<scope>): <subject>
```

### Types
- `feat`: new feature
- `fix`: bug fix
- `docs`: documentation changes
- `refactor`: code refactoring without behavior change
- `test`: adding or updating tests
- `chore`: build, CI, tooling changes
- `perf`: performance improvements

### Rules
- Subject line ≤ 72 characters
- Use imperative mood: "add feature" not "added feature"
- Lowercase subject, no trailing period
- Body (optional): wrap at 72 chars, explain *what* and *why*, not *how*

### Examples
```
feat(propagator): add Born approximation support
fix(born): handle zero-amplitude edge case
docs: update README with installation instructions
test(born): add unit tests for compression method
```

## Git Workflow

### Committing
1. Stage only intended files (`git add <files>`)
2. Never commit secrets, `.env`, or credentials
3. Write a clear conventional commit message
4. Commit locally first

### Pushing
After each commit, push to origin:
```
git push origin <current-branch>
```

### Branches
- Create feature branches from `main` for new work
- Branch naming: `<type>/<short-description>` (e.g., `feat/born-approx`, `fix/zero-amplitude`)
- Keep branches focused on a single concern

### Pull Requests
When asked to create a PR to upstream:
```bash
gh pr create --repo ar4/deepwave --base main --head abronskii-wq:<branch> --title "<conventional-title>" --body "<description>"
```

### Code Style
- Follow existing code patterns in the repository
- Run `ruff check` before committing (project uses ruff)
- Ensure tests pass before pushing

## Remotes
- `origin` → `https://github.com/abronskii-wq/deepwave.git` (your fork)
- `upstream` → `https://github.com/ar4/deepwave.git` (original)