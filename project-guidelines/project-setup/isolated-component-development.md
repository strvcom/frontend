# Isolated component development

Developing components in isolation allows you to play around with components independently from the rest of your app. You can tweak the state and see how the component behaves under various circumstances. You can test it easily. And, most importantly, you are not dependent on other dependencies and can showcase components interactively in an isolated development environment.

This reduces complexity, removes inconsistency and provides an amazing onboarding experience for new developers joining a project. It also provides a much easier testability of components and, last but not least, it serves as UI documentation — called the **styleguide** of your app.

## Storybook

[Storybook](https://github.com/storybooks/storybook) is a development environment for UI components that helps to browse the component library, view the various states and interactively develop & test.

Storybook is all about writing stories. A story usually contains a single state of one component, almost like a visual test case.

It’s one of the most exciting tools to work with! It improves your performance and, with all of its [add-ons](https://storybook.js.org/addons/) it takes your component development to another level. It helps you to write bulletproof components.

Isolation itself also helps team collaboration. You can have a dedicated UI team working on a number of stories — for example, when the UX team is taking care of its integration. Also, it’s much easier to pair with testers and to implement their test cases.

You should consider using Storybook even when working on a project alone. Once you’re used to it, you’ll realize that you are actually developing faster. And with better quality.

