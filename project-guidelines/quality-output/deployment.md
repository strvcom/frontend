# Deployment

We already covered in [Effective and Consistent workflow](../effective-and-consistent-workflow/continuous-integration-delivery.md) chapter, that deployment shouldn’t be done manually - continuous delivery should be used to achieve the best results. But now let’s focus on where and how the solution should be deployed.

## Deployment services

There are many services available. Let’s focus on the main services we use.

### Heroku

[Heroku](https://herokuapp.com) is Platform as a Service. It’s built on top of [AWS](deployment.md#amazon-web-services) and offers nice UI and simple setup. A great choice for server-side rendered apps.

You can set up a development pipeline, easily promote from development to staging, or from staging to production.

Another favorite feature is to set up an auto-deployment from the GitHub branch. Put simply, you just push new changes and they are promoted to Heroku.

The simplicity of installing add-ons makes Heroku a great go-to service. But it gets pretty expensive with scaling.

### Netlify

[Netlify](https://www.netlify.com) is a web development platform with all the stuff needed for static websites. It’s probably the best player in the [JAMStack](https://jamstack.org) world.

It works really nice for static websites. The deploy preview is an amazing feature, which you can set-up for any pull request.

Netlify also offers the following add-ons:

- Analytics
- Functions
- Identity
- Forms
- Large Media

And the majority of the features are free for small or personal projects.

### Amazon Web Services

Amazon Web Services \(AWS\) offers AWS EC2 or AWS S3 combined with Amazon CloudFront. It’s the cheapest and most scalable solution. But it’s the most difficult to set up.

### Now, Firebase

There are many great alternatives. [Now](http://now.sh/) has great support for [monorepos](../effective-and-consistent-workflow/code-structure-architecture.md#monorepos). [Firebase Hosting](https://firebase.google.com/products/hosting/) works nice for static content, but Netlify seems to be better.

## Static vs. server-side

Differences between each are described in [Project Setup](../project-setup/project-starter.md#which-one-to-choose). To have a quality output, you must know what are the benefits of each solution.

Static\(-ally generated\) websites work great with [Netlify](deployment.md#netlify) or other static hosting combined with [CDN](deployment.md#content-delivery-network-cdn).

The server is needed for dynamic data or the server is needed to run some backend tasks. Though, it’s recommended to decouple things. Go serverless or use a monorepo.

## Docker

Kindly borrowed from [https://opensource.com/resources/what-docker](https://opensource.com/resources/what-docker)

[Docker](https://www.docker.com) is a tool designed to make it easier to create, deploy, and run applications by using containers. Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and ship it all out as one package. By doing so, thanks to the container, the developer can rest assured that the application will run on any other Linux machine regardless of any customized settings that machine might have that could differ from the machine used for writing and testing the code.

In a way, Docker is a bit like a virtual machine. But unlike a virtual machine, rather than creating a whole virtual operating system, Docker allows applications to use the same Linux kernel as the system that they're supposed to run on and only requires applications to be shipped with things not already running on the host computer. This gives a significant performance boost and reduces the size of the application.

And importantly, Docker is an open source. This means that anyone can contribute to Docker and extend it to meet their own needs if they need additional features that aren't available out of the box.

Docker is great for the backend. But it’s also suitable for larger and especially server-side rendered apps.

## Continuous delivery

You can read what is Continuous Delivery and why you should use it in [the Project Setup chapter](../project-setup/continuous-integration-delivery.md#continuous-delivery).

Both Heroku and Netlify has build-in Continuous delivery. For AWS S3 you can set up AWS CodeBuild with AWS CodePipeline.

## Content Delivery Network \(CDN\)

For serving any static content or assets, the best approach is to use CDNs. Netlify uses [its own](https://www.netlify.com/products/edge/). [AWS CloudFront](https://aws.amazon.com/cloudfront/) integration like a charm with any other AWS product. You can easily install [Fastly](https://www.fastly.com)[add-on on Heroku](https://elements.heroku.com/addons/fastly). Or use the [Cloudflare](https://www.cloudflare.com).

There are clearly many ways how to use, but why?

### What is a CDN and how does it work?

A CDN is a way to deliver content from your website or mobile application to people more quickly and efficiently, based on their geographic location. A CDN is made up of a network of servers \(“points of presence,” or POPs\) in locations all over the world.

### Some of the benefits of using a CDN for your website

- Faster load times for web and mobile users
- Quickly scalable during times of heavy traffic
- Minimizes risk of traffic spikes at point of origin, ensuring site stability
- Decreases infrastructure costs due to traffic offloading \(less load on origin\)
- Better site performance

### Additional resources

- [Why you should use a content delivery network](https://www.fastly.com/blog/why-you-should-use-content-delivery-network) by Fastly
