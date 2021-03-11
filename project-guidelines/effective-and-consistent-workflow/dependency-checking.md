# Dependency checking

We live in a world of components and dependencies. There are numerous libraries available to perform almost any task. Sometimes, it makes sense to use battle-tested libraries written by large companies. Other times, you should go with your own solution.

No matter what, your project will end up with a dependency tree. It’s good practice to know what you are installing. You should avoid vulnerable packages, or legacy ones without any activity.

## Security

Some of the packages could be vulnerable. Check if they’re ok. A pretty good hint is a small number of downloads or poor GitHub activity. Be cautious.

GitHub does a great job with Security Alerts. But there are also other leading companies doing it even better. Consider using [snyk](https://snyk.io/) for your projects!

Security is mainly needed for [the output](../quality-output/security.md), not the development. But you should think about security concerns at all times.

## Keep your dependencies up to date

Dependencies become out of date pretty much every day. This can be caused by a security update, new features or just a performance update.

You shouldn’t install dependencies with poor GitHub activity. It’s a sign that the project is not maintained anymore.

For already existing dependencies, you can locally use the amazing [npm-check-updates](https://www.npmjs.com/package/npm-check-updates) Unfortunately, you can’t automate them. But sometimes it is handy, especially when you are taking over somebody else’s \(legacy\) codebase. Or you are coming back to your own pet project.

For the projects you are currently working on, you should consider setting up [Dependabot](https://dependabot.com).It got acquired by GitHub and is now fully free of charge! It also works nicely with security updates.

