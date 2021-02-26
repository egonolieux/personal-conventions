# Git conventions

- Do not commit code that does not build to the repository, with the exception of work in progress branches.
- Do not commit untested code to the `master` or `main` branch.
- Stable releases (commits in the `master` or `main` branch) should be tagged by their version number.
- Keep commits small: 1 conceptual change per commit.
- Push often to avoid conflicts (also see <https://en.wikipedia.org/wiki/Bus_factor>).
- Prefer using `git rebase` over `git merge` when possible.
- Use `git merge --squash` or `git rebase -i` to remove work in progress or redundant commits from the history.
- Do not store credentials of any kind in repositories. Always refer to them externally.

## Commit messages

- Separate the subject and the body of the message by a blank line (body is optional).
- Do not end the subject with a period.
- The subject should be written in the imperative mood.
- Keep the subject as short as possible for better readability (preferably <= 80 characters).
- Use proper capitalization.
- Use the body to explain **what** and **why** instead of **how**.

## Branches

- Only use lowercase alphanumerical characters, separated by the `-` character.
- Do not start branch names with a number.
- Use the name of the feature or a short description for the branch name.
- Always suffix work in progress branches with `-wip`.
