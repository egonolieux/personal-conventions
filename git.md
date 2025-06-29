# Git conventions

- Always remove work in progress or redundant commits from the history (see `git merge --squash` or `git rebase -i`).

- Do not commit code that does not build to the repository, with the exception of work in progress branches.

- Do not commit untested code to the `master` or `main` branch.

    The `master` or `main` branch represents a stable version of the project and is often automatically deployed into production.

- Do not put multiple projects into a single repository.

    Having a single project per repository provides proper separation for issue tracking and build automation.

- Do not store credentials of any kind in repositories. Always refer to them externally.

    Keep credentials in a secure environment such as a password manager. It might also be hard to get rid of the credentials once they are in the Git history.

- Keep commits small: 1 conceptual change per commit.

- Prefer using `git rebase` over `git merge` when possible.

    This avoids poluting the Git history.

- Push often to avoid conflicts (also see <https://en.wikipedia.org/wiki/Bus_factor>).

- Tag stable releases (commits in the `master` or `main` branch) by their version number.

## Commit messages

- Do not end the subject with a period.
- Keep the subject as short as possible for better readability (preferably <= 80 characters).
- Separate the subject and the body of the message by a blank line (body is optional).
- Use proper capitalization.
- Use the body to explain **what** and **why** instead of **how**.
- Write the subject in the imperative mood.

## Branches

- Branch names must have 3 parts: the prefix (see prefixes), the issue ID, and a descriptive name, e.g., `task/1/home-page-redesign`. If no issue ID is available, it can be left out, e.g., `task/home-page-redesign`.
- Only lowercase and alphanumerical characters are allowed for the name parts, where each word must be separated by the `-` character.
- Try to keep the descriptive part of the name short.
- Use the `-wip` suffix for work in progress branches, e.g., `task/1/home-page-redesign-wip`.

### Prefixes

- `bugfix`: Bug fixes.
- `hotfix`: Fixes that are not part of the normal development and testing process.
- `task`: A task of any kind, such as new functionality or an improvement.
