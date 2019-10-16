# Code versioning and review flow

GitHub comes with nice code versioning flows. Usually, this is happening through Pull Requests, which could be reviewed by other colleagues on the project.

There are a lot of git guidelines available online. Take a look at [STRV Guidelines](https://github.com/strvcom/strv-guidelines/blob/master/git.md).

Contribution guide to the project, issue templates or pull request templates puts everything on another level. Yet another thing to consider.

## Code reviews

Proper and regular code reviews improve the quality of the whole project. Also even though it is extra work it actually saves a lot of time.

- Fewer bugs and risks are getting merged to the codebase.
- It helps to understand the project more and be more familiar with it.
- Code reviews are great for learning.
- On GitHub, you can enforce code reviews in the branch settings.
- You should automate some common checks by using a Continuous Integration service. For example, you should run here linters and tests. Also, consider using [https://github.com/danger/danger-js](https://github.com/danger/danger-js). The point is to automate as much as possible. And let human-reviewer think about harder problems.
- [https://google.github.io/eng-practices/review/reviewer/](https://google.github.io/eng-practices/review/reviewer/)

## Commit history

- It’s important to have a readable commit history.
- A commit should always address just one logical part.
- Don’t do “Fix typo” and similar commits, but rather amend them to the previous ones.
- Write meaningful commit messages and enforce it buy using commitlint
- Consider using the “Squash and merge” pull request option on GitHub. It leads to a beautiful history, thus a better readability. Also you can easily revert newly merged changes, because they are represented by one single commit.
- Use commitlint, textlint or other handy packages from [code-quality-tools](../project-setup/code-quality-tools.md)
