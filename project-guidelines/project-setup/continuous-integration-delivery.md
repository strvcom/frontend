# Continuous Integration & Delivery

## Continuous integration

Continuous Integration (CI) services can run your tests in several environments: different operating systems, browsers or Node versions. It would be complicated to set up on your local machine. Usually, CI checks every commit to your master or development branch as well as on each pull request — CI will prevent merge or deploy if there are any errors. It’s a common practice to run long processes on CI: integration tests, code coverage reports, etc. Some projects even publish new releases automatically on CI.

Continuous integration will help you to be sure that your project works in all supported environments, and will prevent you from publishing a new version with a regression.

## Continuous Delivery

This chapter is kindly borrowed from [https://continuousdelivery.com](https://continuousdelivery.com/)

Continuous Delivery is the ability to get changes of all types — including new features, configuration changes, bug fixes and experiments — into production, or into the hands of users, safely and quickly in a sustainable way.

Our goal is to make deployments — whether of a large-scale distributed system, a complex production environment, an embedded system, or an app — predictable, routine affairs that can be performed on demand.

CD ensures that code is always in a deployable state even in the face of teams of thousands of developers making changes on a daily basis. We thus completely eliminate the integration, testing and hardening phases that traditionally followed “dev complete”, as well as code freezes.

### Why continuous delivery?

It is often assumed that if we want to deploy software more frequently, we must accept lower levels of stability and reliability in our systems. In fact, [peer-reviewed research](https://continuousdelivery.com/evidence-case-studies/#research) shows that this is not the case—high-performance teams consistently deliver services faster and more reliably than their low performing competition. This is true even in highly regulated domains such as financial services and government. This capability provides an incredible competitive advantage for organizations that are willing to invest the effort to pursue it.

Fundamental practices of continuous delivery help us achieve several important benefits:

- Low-risk releases.The primary goal of continuous delivery is to make software deployments painless, low-risk events that can be performed at any time, on-demand. By applying [patterns](https://continuousdelivery.com/implementing/patterns/) such as [blue-green deployments](http://martinfowler.com/bliki/BlueGreenDeployment.html) it is relatively straightforward to achieve zero-downtime deployments that are undetectable to users.
- Faster time to market. It’s not uncommon for the integration and test/fix phase of the traditional phased software delivery lifecycle to consume weeks or even months. When teams work together to automate the build, deployment, environment provisioning, and regression testing processes, developers can incorporate integration and regression testing into their daily work and completely remove these phases. We also avoid the large amounts of re-work that plague the phased approach.
- Higher quality.When developers have automated tools that discover regressions within minutes, teams are freed to focus their effort on user research and higher-level testing activities such as exploratory testing, usability testing, and performance and security testing. By building a [deployment pipeline](https://continuousdelivery.com/foundations/test-automation/), these activities can be performed continuously throughout the delivery process, ensuring quality is built in to products and services from the beginning.
- Lower costs. Any successful software product or service will evolve significantly over the course of its lifetime. By investing in build, test, deployment and environment automation, we substantially reduce the cost of making and delivering incremental changes to software by eliminating many of the fixed costs associated with the release process.
- Better products.Continuous delivery makes it economical to release in small batches. This means we can get feedback from users throughout the delivery lifecycle based on working software. Techniques such as [A/B testing](http://www.infoq.com/presentations/controlled-experiments) enable us to take a [hypothesis-driven approach to product development](https://www.thoughtworks.com/insights/blog/how-implement-hypothesis-driven-development) whereby we can test ideas with users before building out whole features. This means we can avoid the [2/3 of features we build that deliver zero or negative value](http://stanford.io/130uW6X) to our businesses.
- Happier teams.[Peer-reviewed research](https://continuousdelivery.com/evidence-case-studies/#research) has shown continuous delivery makes releases less painful and reduces team burnout. Furthermore, when we release more frequently, software delivery teams can engage more actively with users, learn which ideas work and which don’t, and see first-hand the outcomes of the work they have done. By removing the low-value painful activities associated with software delivery, we can focus on what we care about most—continuously delighting our users.

If this sounds too good to be true, bear in mind: continuous delivery is not magic. It’s about continuous, daily improvement—the constant discipline of pursuing higher performance by following the heuristic “if it hurts, do it more often, and bring the pain forward.”

## Benefits

- Scalability
- Availability
- Developer’s time saved on deployment
- Internal security
- Adding rollback possibility

## Risks you can incur by not implementing the measure

- If the measure is not implemented, you risk not being able to handle the traffic.
- Meaning no auto-scaling (no reactive way to scale).
