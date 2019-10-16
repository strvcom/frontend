# Continuous Integration & Delivery

Both [Continuous Integration](../project-setup/continuous-integration-delivery.md#continuous-integration) and [Continuous Delivery](../project-setup/continuous-integration-delivery.md#continuous-delivery) are again described in the Project Setup chapter. Without having them present on a project you can hardly guarantee you are working effectively. Consistency is questionable because you can run many tasks/scripts by using git hooks. These are unfortunately something you can skip by using --no-verify flag or editing files directly from GitHub. The Continuous Integration is the only viable checker you can have.

Even though sometimes it can be very hard to set up, there are just too many benefits of using it, so you should always consider setting up these services.

For example, [Netlify](../quality-output/deployment.md#netlify) offers CI/CD for free and almost without any configuration. It also provides amazing preview-deploys out of the box. Or setting up a GitHub Actions, Circle CI or Travis pipelines is also very straightforward. There are many options to choose from. It doesn’t matter how easy or difficult it is to set up. You should use any.

