# Enforcing good practices

Any code quality tool mentioned above without a proper enforcing actually doesn’t make much sense. You never know who is going to work on your project, so rather than hoping that somebody will follow your rules on a project, just use some enforcing measurements and profit from a more quality code.

## Editor integration

Code editors and IDEs support all of the code quality tools. They are doing great suggestions, displaying bugs directly in the code, doing a handy auto-completion.

Attaching some scripts to “On Save” or “On Paste” events \(e.g. Format on Save\) can do the trick.

Then you can have configuration files in your repository. But unfortunately, you can’t enforce using the specific editor.

## Git hooks

To make sure that code pushed to the repository is satisfying all code quality checks you set up, you should use pre-commitand pre-pushhooks provided by [husky](https://github.com/typicode/husky). You can run in them any scripts including the code quality ones. You should use [lint-staged](https://github.com/okonet/lint-staged) to improve performance by running linters just on staged files.

Remember that many rules are auto fixable. Thus, when using `--fix` flag on your staged files, you also need to `git add` again.

Unfortunately, git hooks could be skipped by running the commit with `--no-verify` flag.

## Continuous Integration

The only check you can really enforce is what is running on your Continuous Integration \(CI\) service. It also speeds up your local development \(when using editor integration and no git hooks\).

CI also provides nice information about Pull Requests \(PRs\). You can run there much more and profit from shared information into PR’s comments section.

It also indicates if checks passed or if there is an issue. Which helps to do a code review a bit faster.

