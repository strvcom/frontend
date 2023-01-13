# Frameworks

## Benefits

To have successful software, you need to have a great foundation. It needs to be scalable, easy to upgrade and easy to maintain.

The days when every React project had to be pieced together via elaborate Webpack configuration are behind us, and now we can take advantage of frameworks such as [Next.js](https://nextjs.org/) or [Remix](https://remix.run/). Each of them has a different use case, but they share the same idea: combine the latest web technologies under **one package**. Which is just perfect!

You get \(for free\):

- new features, bug fixes and security updates with a simple - update of ONE package
- easy maintenance
- great documentation
- built and maintained by a huge community and technology leaders

## Risks of not using frameworks

The main risk of having dozens of dependencies is that eventually, you’ll inevitably need to upgrade. There are many updates for each library, and you can't just update them all. You also need to ensure that this update doesn't harm anything. This can sometimes make updates really difficult, and therefore can result in a project becoming more and more outdated. This could even happen during development—which basically means that a project that hasn’t been finished yet can already become outdated. And outdatedness brings with it a lot of security problems, performance issues or a worse developer experience.

So why bother with this headache? Just rely on the tools mentioned above and focus on your app.

### Next.js

Next.JS is the best choice in most cases. It works best for server-side rendered applications, but can also be used for client-side and statically exported websites. It works equally well with content-driven websites regardless of the amount of content.

Pros

- Created by Vercel
- Provides outstanding server-side capabilities
- SEO/SMO friendly
- Works just as well for applications that don't require SSR
- Has static export
- Can combine server-side rendering with static export
- Good choice when you need to handle secrets (aka API keys that must not be exposed on the client)

Cons

- With server comes huge responsibility: security
- Uses framework-specific abstractions such as `getServerSideProps`, so when doing a refactor to another framework, it requires extra effort

### Remix

Remix is a great solution for full-stack web applications. It can be used in a similar way as Next.JS, but it gives best results when used in a full-stack way, meaning that instead of having communication between the client and the backend via APIs, web native form-submission based interaction is used.

Pros

- Easy form handling
- Eliminates the need for network layer
- Layouts and nested routing
- Relies on native web features rather than framework-specific abstractions
- Can be deployed on edge infrastructure

Cons

- Requires mental shift as some "ways" of doing React in other frameworks don't apply (network calls, form handling)
- Requires some knowledge of backend technologies and best practices

## Additional information

Rendering on the web is a difficult topic. It wasn’t that long ago that rendering was the responsibility of backend engineers. Today, it’s the job of a fullstack developer.

Luckily, there are many great resources available. Big kudos to Jason Miller and Addy Osmani for putting together an article on Google Developers: [https://developers.google.com/web/updates/2019/02/rendering-on-the-web](https://developers.google.com/web/updates/2019/02/rendering-on-the-web)

![Infographic showing the spectrum of options described in this article](../../.gitbook/assets/rendering-on-web.png)

Last note: Sometimes it’s really hard to make the right choice, even for skilled developers. Don’t be shy and ask senior devs for their opinions. They can help and guide you — not just in picking the correct framework, but in anything you need. Find yourself a mentor. And, later on, strive to **become a mentor yourself**. Because teaching is the best way of learning.
