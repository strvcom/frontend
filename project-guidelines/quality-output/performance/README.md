# Performance

**Web is fast, web is slow**. Your app should be accessible to all users, regardless if they are on a super-fast fiber network or on a 3G/2G. You can have an amazing app running super fast, but if users are not able to load it, it’s useless.

There are many studies about how page load time actually affects conversion rates. After 2014, mobile usage has taken over desktop use; since then, we've needed to focus on mobile first. And mobiles are unfortunately prone to be on a slow network.

The math here is simple. The less data there is to load, the faster the load is.

Tools like [Lighthouse](https://developers.google.com/web/tools/lighthouse/) and [Webpack Bundle Analyzer](https://github.com/webpack-contrib/webpack-bundle-analyzer) help you analyze your output and improve the overall user experience.

Performance plays a major role in the success of any online venture. Please follow [Why Performance Matters](https://developers.google.com/web/fundamentals/performance/why-performance-matters/) on Google’s Web Fundamentals. Take an extra look on provided _case studies_. It’s obvious that when a web app is faster, it’s more successful.

- https://wpostats.com/ - Case studies and experiments demonstrating the impact of web performance optimization (WPO) on user experience and business metrics.
- https://speedcurve.com/benchmarks/

## Loading Performance

Loading performance is all about how fast the end-user will see your app. There are a few terms you should be aware of:

- Time to First Byte \(TTFB\) - seen as the time between clicking a link and the first bit of content coming in.
- First Paint \(FP\) - the first moment any pixel becomes visible to the user.
- First Contentful Paint \(FCP\) - the time when requested content \(article body, etc.\) becomes visible.
- Time To Interactive \(TTI\) - the time at which a page becomes interactive \(events wired up, etc.\).

> [https://developers.google.com/web/updates/2019/02/rendering-on-the-web\#terminology](https://developers.google.com/web/updates/2019/02/rendering-on-the-web#terminology)

The audit tools mentioned above will help you fix the majority of issues with loading performance.

### How to improve loading performance?

- Service Workers
- Lazy loading images
- [Optimizing bundle size](./bundle-size.md)
  - Minification
  - Code splitting
  - Tree shaking
- [CDN](./deployment.md#content-delivery-network-cdn)

## Runtime Performance

Runtime Performance is more about how smooth and fluid your app is. You should aim to have 60fps all the time. You can use Chrome’s flame chart, which visualizes JavaScript performance. Also, there is the FPS meter.

### How to improve runtime performance?

- [react-window](https://github.com/bvaughn/react-window) - React components for efficiently rendering large lists and tabular data
- WebGL for hardcode web animations accelerated by GPU
- web-workers
- WebAssembly

## Articles

- [20 Ways to Speed Up Your Website and Improve Conversion in 2019](https://www.crazyegg.com/blog/speed-up-your-website/)
- [Smashing Magazine's Frontend Performance Checklist 2020](https://www.smashingmagazine.com/2020/01/front-end-performance-checklist-2020-pdf-pages/)
- [2019 Page Speed Report for Marketers](https://unbounce.com/page-speed-report/)
- [Industry Benchmarks on Mobile Page Speeds](https://www.thinkwithgoogle.com/intl/en-aunz/advertising-channels/mobile/au-mobile-page-speed-new-industry-benchmarks/)
- [Impact on conversion rates](https://www.portent.com/blog/analytics/research-site-speed-hurting-everyones-revenue.htm)
- [Mobile pages speeds](https://www.thinkwithgoogle.com/marketing-resources/experience-design/mobile-page-speed-load-time/)
- [How fast should a website load?](https://www.hobo-web.co.uk/your-website-design-should-load-in-4-seconds/)
- [Value of speed](https://web.dev/value-of-speed/)
- [Google Mobile Site Speed Playbook](https://www.thinkwithgoogle.com/_qs/documents/3975/c676a_Google_MobileSiteSpeed_Playbook_v2.1_digital_RD1XArd.pdf)
