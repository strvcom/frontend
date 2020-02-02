# Code Quality Tools

The quality of code results in the **quality of the app**. If the code is well written, it’s much easier to **scale**, **maintain** or do **refactoring**. A well documented and well-typed project helps to **onboard** new developers.

There are many tools that can analyze your code before it goes to production.

## Formatting

A code can be written in many ways. There are different styles. A unified style on a project helps to move faster, especially for newcomers. Enforcing it on the organizational level will bring more pros than cons to everybody on your team.

It's recommended to follow the same formatting on a project. This makes the code more consistent and readable. It also removes unnecessary discussions about whether it should be formatted in this or that way. Formatting itself doesn't have any influence on the output. The functionality is always the same. But what it makes important is the **developer experience**. For teams working on a project, it's useful to set their preferred style of writing code. This is also very beneficial for any new member joining a project, since it makes his/her onboarding much easier.

### EditorConfig

EditorConfig helps maintain consistent coding styles for multiple developers working on the same project across various editors, IDEs and operating systems. The EditorConfig project consists of a file format for defining coding styles and a collection of text editor plugins that enable editors to read the file format and to adhere to defined styles. EditorConfig files are easily readable and they work nicely with version control systems.

All you need is to have a .editorconfig file present in your project folder and EditorConfig plugin installed in your editor; it will automatically enforce a consistent code style. No more discussions if the tab size should be 2 or 4 spaces. No more tabs vs. spaces wars.

### Prettier

Prettier is an opinionated code formatter with the great support of all frontend related syntaxes, including JSX and GraphQL. You can set it up however you want and it will automatically transform into a consistent style.

Prettier increases productivity and reduces unnecessary discussions by making code more readable. Even if Prettier does not format all code 100% the way you'd like, it's worth the "sacrifice" given the unique benefits of Prettier, don't you think?

It’s very simple to integrate Prettier into your code editor and workflow. Use it as pre-commit hooks, a separate script, in continuous integration or just invoke it when saving files in your editor.

It seems a bit weird in the beginning, but the adoption process is quite straightforward and you will start to love Prettier!

Take a look at the official documentation on the Why Prettier page: [https://prettier.io/docs/en/why-prettier.html](https://prettier.io/docs/en/why-prettier.html)

## Linting

Linting is the process of running a program that will analyze code for potential errors. It's essential for programming. Linting helps you catch bugs and follow best practices during development, thus making production code more stable.

Just like Prettier, all the linters can be automated and integrated into your workflow and code editor.

### ESLint

ESLint is a popular linter for JavaScript. While it’s primarily used to capture language-related issues, it can also be used to enforce code style and good practices. It can fix many issues automatically, especially code style. You can write your own rules to ensure code consistency within your team or organization.

JavaScript doesn’t have an official coding style, but the community maintains a few. Airbnb and Standard are especially popular. Airbnb is detailed and pragmatic, while Standard is a bit controversial because it doesn’t use semicolons. Semistandard is a variant that fixes that issue. These options use two spaces for indentation.

At STRV, we maintain our own ruleset—with a huge focus on our coding style. We believe that ESLint rulesets can have many errors that aren’t real errors, and on the other hand, they sometimes have warnings which we consider errors.

### TSLint

TSLint is a linter for TypeScript, but today it’s completely unnecessary. Instead, you can use the ESLint with a `@typescript-eslint` plugin.

### stylelint

If there is any custom CSS that must be linted as well, [Stylelint](https://stylelint.io/) does a great job with that. Besides catching silly typos and bugs, stylelint can enforce styleguide and disable the usage of unwanted units or wrong notations.

Just like other tools, it has great editor integration and a lot of plugins.

## Contribution tools

When it comes to project contribution, there are some good practices you can do in your commits. Doing better commits also helps you to become a better programmer. Why not use yet another set of tools to help yourself?

### commitlint

Using [Conventional commits](https://www.conventionalcommits.org) looks like a nice practice, helping the readability of commit history.

You can use [commitzen-cli](https://github.com/commitizen/cz-cli) to become a better "commitzen" and improve your commit flow.

### textlint

Textlint works like a spellchecker of your code and commit messages. It improves readability and decreases confusion stemming from silly typos or mistakes.

You can set up a dictionary for a list of libraries you are using. Overall, this leads to a better quality of documentation.

## code-quality-tools

At STRV, we maintain a [code-quality-tools](https://github.com/strvcom/code-quality-tools) monorepository with our own configurations for many tools mentioned above. We highly recommend them. If you disagree with anything, please don’t disable it, but rather open an issue or a discussion.

Be brave and convince clients to move forward with our ruleset. It’s battle-tested and based on numerous successful projects.

Also, our coding style will make your code beautiful.
