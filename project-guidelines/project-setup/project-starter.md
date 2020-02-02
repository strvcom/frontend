# Project starter

## Benefits

To have successful software, you need to have a great foundation. It needs to be scalable, easy to upgrade and easy to maintain.

The best approach are **zero-config** solutions such as [Create React App](https://facebook.github.io/create-react-app/), [Next.js](https://nextjs.org/) or [Gatsby.js](https://www.gatsbyjs.org/). Each of them has a different use case, but they share the same idea: combine the latest web technologies under **one package**. Which is just perfect!

You get (for free):

- new features, bug fixes and security updates with a simple - update of ONE package
- easy maintenance
- great documentation
- all cured by a huge community and technology leaders

## Risks of not using zero-config project starters

The main risk of having dozens of dependencies is that eventually, you’ll inevitably need to upgrade. There are many updates for each library, and you can't just update them all. You also need to ensure that this update doesn't harm anything. This can sometimes make updates really difficult, and therefore can result in a project becoming more and more outdated. This could even happen during development—which basically means that a project which hasn’t been finished yet can already be outdated. And outdatedness brings with it a lot of security problems, performance issues or a worse developer experience.

So why bother with this headache? Just rely on the tools mentioned above and focus on your app.

## Project starters

There are numerous zero-configuration project starters. Each of them serves a different purpose. Yet in a React ecosystem, there are many similar projects that attempt to achieve the same result. There are also other JavaScript alternatives, like Vue.js or Angular. But since we only work with React and we’re speaking from STRV’s perspective, let’s take a closer look at our choice:

### Create React App

Pros

- Created and maintained by Facebook
- Biggest community
- High-quality contributors \(for example, Tobias Koppers a.k.a. sokra - creator of webpack, Kent C. Dodds and of course amazing React Core team\)
- Well-known by almost every React developer, which leads to easier onboarding
- Has outstanding documentation
- Provides maximum freedom

Cons

- Tools are preconfigured to work in a specific way, which can only be changed by “ejecting” \(something we strongly recommend you do not do; instead, go with react-app-rewired or create-strv-app or any other fork of the main repository\)
- Requires extra work to achieve the same capabilities as Gatsby or Next.js

### Next.js

Pros

- Created by Zeit
- Provides outstanding server-side capabilities
- Has static export
- Can combine server-side rendering with static export

Cons

- With server comes huge responsibility: security
- Uses framework-specific abstractions such as `getInitialProps`, so when doing a refactor to another framework, it requires extra effort

### Gatsby

Pros

- One of the best static-site generators
- Has tons of plugins
- GraphQL API for pulling data
- Uses MDX
- Gatsby Themes
- A built-in full toolkit of web developers, including image optimization

Cons

- Without incremental builds (e.g. just some pages were changed, but build command has to rebuild everything), it can be a bit slow. [Gatsby Cloud](https://www.gatsbyjs.com/cloud/) is the nice solution for the problem.
- Because of a lot of internal logic, there is a much harder learning curve

## Which one to choose?

To avoid unnecessary headaches and refactoring during development, It’s very important to choose wisely. As a developer, you must know your app’s exact purpose. Is it a simple landing page displaying a basic introduction of a product or company? Or are you building an e-commerce solution?

At first sight, it may seem like it doesn’t matter because we develop the app in React and it will therefore be a Single Page Application. But in fact, it matters a lot. Based on the established purpose of the app, we can decide on the ideal project starter. Some are good for static export, some for server-side rendering, some just for client rendering.

There are a few basic rules that help you decide.

### Client-side rendering

- Your app requires user authentication
- You don’t care about [SEO](../quality-output/seo-smo.md)
- You are planning to implement your own routing
- A typical example: [Tinder PWA](http://www.tinder.com)
- Project starter: Create React App

### Static export

- You care about loading performance
- You care about SEO
- Static \(hardcoded\) content
- Content doesn’t change that often
- A lot of dynamic content will be possible with [incremental builds support](https://github.com/gatsbyjs/gatsby/issues/5002#issuecomment-531653471)
- [Gatsby-plugin-netlify-cache](https://github.com/axe312ger/gatsby-plugin-netlify-cache) to speed up build time by 10x
- [Gatsby Cloud](https://www.gatsbyjs.com/cloud/)
- A typical example: [www.lubosmid.com](https://www.lubosmid.com/)
- Project starter: Gatsby, Next.js, Create React App turned into react-static or react-snap

### Server-side rendering

- You care about SEO
- A lot of dynamic content
- You need to “hide” secrets \(API keys, credentials to 3rd party services\) which will be otherwise exposed in the client JavaScript bundle.
- You need maximum scalability with your infrastructure.
- Easier A/B testing
- A typical example: [www.littlespoon.com](https://www.littlespoon.com/)
- Project starter: Next.js, Create-React-App turned into Razzle

Both Gatsby and Next.js provide a lot of utilities out of the box. Built-in code-splitting, simple client-side routing, outstanding development experience (Hot Module Replacement) and numerous plugins and tutorials. So, why should you bother with Create React App, which is missing a lot of things that must be added if you’re aiming for an experience similar to what you get with Gatsby and Next.js?

The answer is simple: Create React App provides you with full control over your web app. Meaning that you can adjust it based on your needs while not being limited by predefined solutions.

Additionally, it’s quite easy to refactor it to serve another purpose. But as mentioned above, no need to worry about refactoring if you make wise choices from the very beginning.

## Additional information

Rendering on the web is a difficult topic. It wasn’t that long ago that rendering was the responsibility of backend engineers. Today, it’s the job of a fullstack developer.

Luckily, there are many great resources available. Big kudos to Jason Miller and Addy Osmani for putting together an article on Google Developers: [https://developers.google.com/web/updates/2019/02/rendering-on-the-web](https://developers.google.com/web/updates/2019/02/rendering-on-the-web)

![Infographic showing the spectrum of options described in this article](../../.gitbook/assets/rendering-on-web.png)

Last note: Sometimes it’s really hard to make the right choice, even for skilled developers. Don’t be shy and ask senior devs for their opinions. They can help and guide you — not just in picking the correct project starter, but in anything you need. Find yourself a mentor. And, later on, strive to **become a mentor yourself**. Because teaching is the best way of learning.

## Templates

Besides a good project starter, you also need to have code quality tools, a testing library and much more. Why not automate the job with curated Github templates?

- [strvcom/template-react-cra](https://github.com/strvcom/template-react-cra)
- [strvcom/template-react-next.js](https://github.com/strvcom/template-react-next.js)
- [strvcom/template-react-native](https://github.com/strvcom/template-react-native)
- more on [strv.io](https://www.strv.io/)
