# Enforcing good practices

All code quality tools mentioned above don’t actually make much sense without being properly enforced. You never know who is going to work on your project. So, rather than hoping that somebody will follow your rules, just use some enforcing measures and profit from code of higher quality.

## Editor integration

Code editors and IDEs support all of the code quality tools. They offer great suggestions, display bugs directly in the code and come with handy auto-completion.

Attaching some scripts to “On Save” or “On Paste” events \(e.g. Format on Save\) can do the trick.

You can then have configuration files in your repository. But unfortunately, you can’t enforce using the specific editor.

## Git hooks

To make sure that code pushed to the repository satisfies all code quality checks that you’ve set up, you should use **pre-commit** and **pre-push** hooks provided by [husky](https://github.com/typicode/husky). You can run in them any scripts, including the code quality ones. You should use [lint-staged](https://github.com/okonet/lint-staged) to improve performance by running linters solely on staged files.

Remember that many rules are auto fixable. Thus, when using `--fix` flag on your staged files, you also need to `git add` again.

Unfortunately, git hooks can be skipped by running the commit with `--no-verify` flag.

## Continuous Integration

The only check you can really enforce is what is running on your Continuous Integration \(CI\) service. It also speeds up your local development \(when using editor integration and no git hooks\).

CI also provides nice information about Pull Requests \(PRs\). There, you can run much more and profit from shared information in the PR’s comment section.

It also indicates if checks passed or if there is an issue. Which makes doing a code review a bit faster.
