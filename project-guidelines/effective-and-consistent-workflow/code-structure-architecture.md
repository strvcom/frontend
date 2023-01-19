# Code structure, architecture

Before you start developing your app, you should think about how to structure it.

We recommend using the “[grouping by feature](https://reactjs.org/docs/faq-structure.html#grouping-by-features-or-routes)” approach, which, in terms of scalability, is better for than “grouping by type”. Besides that, it makes navigating the codebase easier as you get to know all your domain entities and features without digging through the folders.

While grouping by feature is recommended, it's also important to not be too dogmatic. If a different structure makes more sense for you and your team, use it. Remember what the official React Documentation says: “Don’t overthink it. If you’re just starting a project, don’t spend more than five minutes on choosing a file structure. Pick any of the above approaches \(or come up with your own\) and start writing code! You’ll likely want to rethink it anyway after you’ve written some real code.”

What matters in the end is how comfortable the structure is for you and your colleagues, how easy it is to understand and how easy it is to scale.

Be consistent. And ideally, describe your code structure in the projects README file. So anybody else can easily jump into the project and get familiarized.

## Monorepos

Monorepos are a nice way to share code between frontend and backend. Since the STRV backend uses mostly Node.js, we can share a lot of important information—like validation rules, business logic and so on. At the same time, monorepos bring additional complexity and there might be some compromises needed to allow reusability.

For example, sharing validation rules is a good idea, but the BE and FE might use different validation libraries - FE has to find a balance between feature-rich and lightweight libraries, BE doesn't need to worry about that. Also, validation rules might differ, with BE having additional validation that FE doesn't have access to.

Another common artifact to share is type definitions, but in a GraphQL project you can generate those types on the FE without having access to BE source code.

In other words, there's a lot of factors that influence a decision to use or not to use a monorepo setup, and it's important to always weigh its benefits against the drawbacks.

[Monorepo Wikipedia page](https://en.wikipedia.org/wiki/Monorepo) lists some advantages and disadvantages of monorepos.

### Advantages

- Ease of code reuse – Similar functionality or communication protocols can be abstracted into shared libraries and directly imported by projects, without the need of a package manager.
- Simplified dependency management – In a multiple repository environment where multiple projects depend on a third-party dependency, that dependency might be downloaded or built multiple times. In a monorepo, the build can be easily optimized, as referenced dependencies all exist in the same codebase.
- [Atomic commits](https://en.wikipedia.org/wiki/Atomic_commit) – When projects that work together are contained in separate repositories, releases need to sync which versions of one project work with the other. And in large enough projects, managing compatible versions between dependencies can become [dependency hell](https://en.wikipedia.org/wiki/Dependency_hell). In a monorepo, this problem can be negated because developers may change multiple projects atomically.
- Large-scale code refactoring – Since developers have access to the entire project, refactors can ensure that every piece of the project continues to work after a refactor.
- Collaboration across teams – In a monorepo that uses source dependencies \(dependencies that are compiled from source\), teams can improve projects being worked on by other teams. This leads to flexible code ownership.

### Limitations and disadvantages

- Loss of version information – Although not required, some monorepo builds use one version number across all projects in the repository. This leads to a loss of per-project semantic versioning.
- Lack of per-project security – With split repositories, access to the repository can be granted based upon need. A monorepo allows read access to all software in the project, possibly presenting new security issues.
- More storage needed – With split repositories, you can fetch only the project you are interested in. With a monorepo, you'll typically have to fetch all the repositories. Note that there are mitigations to this \(like partial fetching\).

### Managing monorepos

You can use [Nx](https://nx.dev/) or [Turborepo](https://turbo.build/) or [yarn workspaces](https://yarnpkg.com/lang/en/docs/workspaces/) to better manage the monorepos.

### Final Thoughts

> Kindly borrowed from Ruan Martinelli's article: [https://www.strv.com/blog/getting-to-know-monorepo-engineering](https://www.strv.com/blog/getting-to-know-monorepo-engineering)

Whether you choose a Monorepo or a Multirepo architecture for your project \(or organization\), you’ll have to deal with trade-offs in both approaches.

Multirepos will bring challenges related to coordination: managing dependencies, doing large-scale refactors, releasing multiple artifacts at once, etc. Monorepos will solve most of these problems, but come with greater complexity when it comes to tooling and managing the scalability of the repository.

With discipline, however, both approaches will work fine at any scale.

And one last note: No matter which architecture you choose, always take into account the engineering culture of your team. Building software is a social activity and different teams have different ways of working and communicating. Always be smart and carefully evaluate your architecture choice based on your specific situation.
