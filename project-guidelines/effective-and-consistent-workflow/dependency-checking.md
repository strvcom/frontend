# Dependency checking

We live in a world of components and dependencies. There are numerous libraries available to perform almost any task. Sometimes it makes sense to use battle-tested libraries written by large companies. Sometimes you should go with your own solution.

Anyways, your project will end up with a dependency tree. It’s a good practice to know what you are installing. You should avoid vulnerable packages, or legacy ones without any activity.

## Security

Some of the packages could be vulnerable. Thus, you should check if it is ok. A pretty good lead is a small number of downloads or poor GitHub activity. Be cautious.

GitHub is doing a great job with Security Alerts. But there are also other leading companies doing it even better. Consider using [snyk](https://snyk.io/) for your projects!

Security is mainly needed for [the output](../quality-output/security.md), not the development. But you should think about security concerns all the time.

## Keep your dependencies up-to-date

Dependencies are getting out of date pretty much every day. It could be caused by a security update, new features or just a performance update.

You shouldn’t install dependencies with poor GitHub activity - it’s a sign that the project is not maintained anymore.

For already existing dependencies you can use locally an amazing [npm-check-updates](https://www.npmjs.com/package/npm-check-updates) which you, unfortunately, can’t automate. But sometimes it’s handy, especially when you are taking over somebody else \(legacy\) codebase. Or you are coming back to your pet project.

For the projects, you are currently working on, you should consider setting up [Dependabot](https://dependabot.com). It got acquired by GitHub and now is fully free of charge! And it also works nicely with security updates.

