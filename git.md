# Git conventions

- Do not commit code that does not build to the repository, with the exception of work in progress branches.
- Do not commit untested code to the `master` or `main` branch.
- Stable releases (commits in the `master` or `main` branch) must be tagged by their version number.
- Keep commits small: 1 conceptual change per commit.
- Push often to avoid conflicts (also see <https://en.wikipedia.org/wiki/Bus_factor>).
- Prefer using `git rebase` over `git merge` when possible.
- Always remove work in progress or redundant commits from the history (see `git merge --squash` or `git rebase -i`).
- Do not store credentials of any kind in repositories. Always refer to them externally.

## Commit messages

- Separate the subject and the body of the message by a blank line (body is optional).
- Do not end the subject with a period.
- The subject must be written in the imperative mood.
- Keep the subject as short as possible for better readability (preferably <= 80 characters).
- Use proper capitalization.
- Use the body to explain **what** and **why** instead of **how**.

## Branches

- Branch names must have 3 parts: the prefix (see prefixes), the issue ID, and a descriptive name, e.g., `feature/1/home-page-redesign`. If no issue ID is available, it can be left out, e.g., `feature/home-page-redesign`.
- Only lowercase and alphanumerical characters are allowed for the name parts, where each word must be separated by the `-` character.
- Try to keep the descriptive part of the name short.
- Work in progress branches must use the `-wip` suffix, e.g., `feature/1/home-page-redesign-wip`.

### Prefixes

- `bugfix`: Bug fixes.
- `doc`: Documentation.
- `experimental`: Experimental features or improvements.
- `feature`: Features or improvements.
- `hotfix`: Fixes that are not part of the normal development and testing process.
- `refactor`: Refactoring or migrations.
