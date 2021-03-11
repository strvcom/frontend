# Continuous Integration & Delivery

Both [Continuous Integration](../project-setup/continuous-integration-delivery.md#continuous-integration) and [Continuous Delivery](../project-setup/continuous-integration-delivery.md#continuous-delivery) are described in the Project Setup chapter. Without having them in a project, it’s difficult to guarantee you are working efficiently. Consistency is questionable because you can run many tasks/scripts by using git hooks. These are unfortunately something you can skip by using `--no-verify` flag or editing files directly from GitHub. Continuous Integration is the only viable checker you can have.

Even though it can sometimes be very hard to set up, the many benefits of using it outweigh the cons. You should always consider setting up these services.

For example, [Netlify](../quality-output/performance/deployment.md#netlify) offers CI/CD for free and without almost any configuration. It also provides amazing preview-deploys out of the box. Similarly, setting up GitHub Actions, Circle CI or Travis pipelines is also very straightforward. There are many options to choose from. It doesn’t matter how easy or difficult it is to set up. It’s worth it.

