# Documentation

First of all it’s important to realize to whom the documentation is intended. This documentation guide is for writing simple technical documentation for other developers \(or yourself in one year\).

In general, documentation should help other developers with on-boarding and continue working on the project. Please make it simple or high level and don't spend too much time with details.

* Introduction - A brief description of the project.
* Getting Started
  * Installation / build / CI instructions
  * List of prerequisites to run a project \(if exists and are not typical\)
  * .env.example or configuration file examples
  * How to run tests
  * Coding conventions - such as architecture, file organization, comments, naming conventions, programming practices
* Useful links & External services
  * Link to API docs \(if exists\)
  * Link to Project Guidelines \(if exists\)
  * Link to [styleguide](../project-setup/isolated-component-development.md) \(if exists\)
  * List of 3rd party services \(requiring login or access\)
  * Brief description of 3rd party services or libraries which are not self-explanatory or the app heavily relies on them
* Important information
  * Document parts of the application with heavy business logic \(parts of the application which would be hard to understand just from code\)
  * List of supported devices \(tablet, smartphone, TV, etc…\)
  * Anything else you consider "must-know" for developers to work on the project
* Deployment & Publish instructions
  * Deployment instructions
  * Brief description of infrastructure
  * app release/publishing instructions if you are building a React Native project

Documentation should ideally be a part of the repository so it will never get lost. Utilizing README.md for this is the preferable way.

Keep in mind that it's a common practice to comment complicated functions/classes directly in code during development.

Also, you are not limited to one single README - you can have as many READMEs as your documentation requires.

Styleguide really helps to have a good overview of the project. Working tests and fully typed codebase is another great source of documentation.

## Markdown Architectural Decision Records

On large scale projects, it could make sense to introduce Architectural Decision Records \(ADR\). Having them in Markdown as a part of a project is a bit more convenient rather than a classical specification of the project in tools like Confluence or similar. The main benefit is, that ADR is being versioned together with your app. So it will stay as a single source of truth.

Learn more about MADR on the official GitHub page: [https://github.com/adr/madr](https://github.com/adr/madr)

This seems to be hardcore, but it’s really helpful for large long-term projects.

