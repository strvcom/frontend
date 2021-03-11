# Documentation

First of all, it’s important to realize for whom your documentation is intended. This documentation guide is for writing simple technical documentation for other developers \(or for yourself one year from now\).

In general, documentation should help other developers with on-boarding and with continuing to work on a project. Please make it simple or high-level, and don't spend too much time with details.

* Introduction - A brief description of the project.
* Getting Started
  * Installation / build / CI instructions
  * List of prerequisites to run a project \(if applicable and if not typical\)
  * `.env.example` or configuration file examples
  * How to run tests
  * Coding conventions - such as architecture, file organization, comments, naming conventions, programming practices
* Useful links & external services
  * Link to API docs \(if applicable\)
  * Link to Project Guidelines \(if applicable\)
  * Link to [styleguide](../project-setup/isolated-component-development.md) \(if applicable\)
  * List of 3rd party services \(requiring login or access\)
  * Brief description of 3rd party services or libraries which are not self-explanatory, or on which the app relies heavily
* Important information
  * Document parts of the application with heavy business logic \(parts of the application which would be hard to understand from code alone\)
  * List of supported devices \(tablet, smartphone, TV, etc…\)
  * Anything else you consider **"must-know"** for developers to work on the project
* Deployment & Publish instructions
  * Deployment instructions
  * Brief description of infrastructure
  * App release/publishing instructions if you are building a React Native project

Documentation should ideally be a part of the repository, so it will never get lost. Utilizing `README.md` for this is the preferred approach.

Keep in mind that it's common practice to comment complicated functions/classes directly in code during development.

Also, you are not limited to one single README. You can have as many READMEs as your documentation requires.

A Styleguide really helps to have a good overview of your project. Working tests and a fully typed codebase are additional great sources of documentation.

## Markdown Architectural Decision Records

On large scale projects, it might make sense to introduce Architectural Decision Records \(ADR\). Having them in Markdown as a part of a project is a bit more convenient than a classical specification of the project in tools like Confluence or similar. The main benefit is that ADR is versioned together with your app. So it will stay as a single source of truth.

Learn more about MADR on the official GitHub page: [https://github.com/adr/madr](https://github.com/adr/madr)

This may seem a little hardcore, but it’s really helpful for large, long-term projects.

