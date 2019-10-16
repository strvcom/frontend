# Code structure, architecture

Before you start developing your app, you should think about how to structure it.

We recommend using “[grouping by feature](https://reactjs.org/docs/faq-structure.html#grouping-by-features-or-routes)” approach, which is better for scalability rather than “grouping by type”. Besides that, it also eliminates possible dead code or assets. And it's much easier to follow.

Yet sometimes it makes sense to group your code in a different way. The official React Documentation says: “Don’t overthink it. If you’re just starting a project, don’t spend more than five minutes on choosing a file structure. Pick any of the above approaches \(or come up with your own\) and start writing code! You’ll likely want to rethink it anyway after you’ve written some real code.”

What matters in the end, how comfortable the structure is for you and your colleagues, how easy it is to understand and how easy it is to scale.

Be consistent. And ideally, describe your code structure in the projects README file. So anybody else can easily jump into the project and feel familiar there.

## Monorepos

Monorepos are a nice way to share code between the frontend and backend. Since the STRV backend is mostly using Node.js, we can share a lot of important stuff like validation rules, business logic and so on. This leads to better scalability and a more robust solution with a decreased amount of bugs.

Sharing the codebase among platforms is not just recommended, but rather the preferred way how to build successful apps. The main drawback is the initial complexity, but you can consider that as a nice investment which will be reflected in a lot of time savings in the future.

Accordingly to [Monorepo Wikipeda page](https://en.wikipedia.org/wiki/Monorepo) there are some advantages and limitations of monorepos.

### Advantages

* Ease of code reuse – Similar functionality or communication protocols can be abstracted into shared libraries and directly imported by projects, without the need of a package manager.
* Simplified dependency management –In a multiple repository environment where multiple projects depend on a third-party dependency, that dependency might be downloaded or built multiple times. In a monorepo the build can be easily optimized, as referenced dependencies all exist in the same codebase.
* [Atomic commits](https://en.wikipedia.org/wiki/Atomic_commit) – When projects that work together are contained in separate repositories, releases need to sync which versions of one project work with the other. And in large enough projects, managing compatible versions between dependencies can become [dependency hell](https://en.wikipedia.org/wiki/Dependency_hell). In a monorepo this problem can be negated, since developers may change multiple projects atomically.
* Large-scale code refactoring – Since developers have access to the entire project, refactors can ensure that every piece of the project continues to work after a refactor.
* Collaboration across teams – In a monorepo that uses source dependencies \(dependencies that are compiled from source\), teams can improve projects being worked on by other teams. This leads to flexible code ownership.

### Limitations and disadvantages

* Loss of version information –Although not required, some monorepo builds use one version number across all projects in the repository. This leads to a loss of per-project semantic versioning.
* Lack of per-project security – With split repositories, access to the repository can be granted based upon need. A monorepo allows read access to all software in the project, possibly presenting new security issues.
* More storage needed – With split repositories, you can fetch only the project you are interested in. With a monorepo, you'll typically have to fetch all the repositories. Note that there are mitigations to this \(like partial fetching\).

### Managing monorepos

You can use [lerna](https://github.com/lerna/lerna) or [yarn workspaces](https://yarnpkg.com/lang/en/docs/workspaces/) \([or both](https://medium.com/hy-vee-engineering/creating-a-monorepo-with-lerna-yarn-workspaces-cf163908965d)\) to better manage the monorepos.

### Final Thoughts

Whether you choose a Monorepo or a Multirepo architecture for your project \(or organization\), you’ll have to deal with trade-offs in both approaches.

Multirepos will bring challenges related to coordination: managing dependencies, doing large-scale refactors, releasing multiple artifacts at once etc. Monorepos will solve most of these problems, but come with greater complexity when it comes to tooling and managing the scalability of the repository.

With discipline, however, both approaches will work fine at any scale.

And one last note: No matter which architecture you choose, always take into account the engineering culture of your team. Building software is a social activity and different teams have different ways of working and communicating. Always be smart and carefully evaluate your architecture choice based on your specific situation.

[https://www.strv.com/blog/getting-to-know-monorepo-engineering](https://www.strv.com/blog/getting-to-know-monorepo-engineering)

