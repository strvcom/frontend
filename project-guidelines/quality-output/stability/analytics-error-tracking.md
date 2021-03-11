# Analytics & Error Tracking

The client or product owner should ideally track all data to get a better image of users: What is their behavior? Which devices do they use? And so on. Another critical piece of information are crash reports of your app, which help you and your team debug bugs during production.

Frontend developers are usually those who implement these analytics and error boundaries connected to crash reporting services. It’s very important to know what you are going to track, and how. Ideally from the very beginning of the project.

A lot of clients underestimate the power of these services. And they see it as yet another extra feature which can be postponed after the MVP release. Help them to understand why it’s important, and why they should care about it.

## Analytics

You can't fix what you can't measure.

Analytics help to understand the behavior of your users. You can track page views, conversion rates or even bugs.

There are many tools for this, like Facebook Pixel or [Adobe Analytics](https://www.adobe.com/cz/analytics/adobe-analytics.html), which are more business or marketing oriented. Let’s focus on these, since they can also provide beneficial information for developers.

### Google Analytics

As an industry-standard, [Google Analytics](https://analytics.google.com/analytics/web/) works really well. The free plan provides a lot of functionality and integration is easy. But it’s a bit heavy in terms of loading performance. You can defer their loading by wrapping them into the setTimeout function.

Or you can go even further and utilize Service Workers to do offline analytics. We highly recommend using it with [Workbox](https://developers.google.com/web/tools/workbox/modules/workbox-google-analytics), which is a great utility library for working with Service Workers developed by Google.

### Netlify Analytics

If you are hosting your web app on [Netlify](https://www.netlify.com), there is a fresh new feature called [Netlify Analytics](https://www.netlify.com/products/analytics/). It works directly on Netlify’s servers, so it doesn’t impact the runtime of your app.

It’s fully GDPR compliant and provides better accuracy and performance. It’s capable of capturing web pages that were not found \(404\).

The only “con” is that the smallest tier is for $9/month.

### FullStory

Large projects can utilize the [FullStory](https://www.fullstory.com) platform. It has many great integrations \(for example with Jira\) and truly provides your users’ full story—including videos from a session, which is an incredible tool for debugging.

The free plan offers one thousand sessions per month. The next tier is for $850/month.

### Segment

One tool to run them all, [Segment](https://segment.com) simply collects the data from users and sends it to other integrated services. It’s easy to scale and to maintain 3rd party services. And it’s cross-platform, so you can use it in native apps, on a server or on the web.

Segment is free for developers. For business, especially those with a bigger user base, it’s a bit expensive.

## Error Tracking

[This great article from KeyCDN](https://www.keycdn.com/blog/error-tracking) says: The key to success in life is learning from your mistakes. The same can be said for web development. Error tracking is a vital component of any web project because it helps you [pinpoint performance problems](https://www.keycdn.com/support/pinpoint-website-performance-issues) before they get out of hand.

Use [Sentry.io](https://sentry.io/welcome/) for error tracking helps developers monitor and fix crashes in real-time.

You can also rely on information provided by analytics services, such as FullStory.

