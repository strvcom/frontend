# Bundle size

## Assets

Images carry most of the weight for a web page. You must always think about the optimization of all images, videos or fonts in a project. You can save megabytes just by running a simple optimization.

Asynchronous loading could tremendously increase loading performance.

### Images

Go for the correct format. Always optimize images \(or serve them through services like Cloudinary\). Consider using webp, if it is possible.

Images must be quality enough, optimized, responsive, loaded fast or lazy-loaded if needed. Lighthouse does a great job with recommendations on how images could be improved.

#### Image formats

Each format is suitable for a different need. Be wise when you are choosing.

* JPG
  * lossy compression
  * great for photos, illustrations or background images
* GIF
  * limited to 256 colors
  * can be transparent \(svg/png/webp is recommended\)
  * can be animated \(but video is recommended\)
  * not much used anymore
* PNG
  * lossless compression
  * images which must have better quality \(logos, infographics, etc.\)
  * can be transparent
  * 8bit or 32bit version
* WEBP
  * a modern image format with improving support, but could be fixed by polyfill
  * provides superior lossless and lossy compression for images on the web
* SVG
  * vector format
  * great for icons
  * can be animated by CSS or JavaScript
  * can even have raster images inside of it

#### Optimization

To reduce image size you can use many [Optimization Tools](bundle-size.md#optimization-tools), but before you choose one you should know how to optimize your images.

* You need to have many responsive images to cover various screen sizes
* Reduce unnecessary image decode and resize costs
* Use srcsetor picture to serve different sizes
* Think of [art direction](https://www.webdesignerdepot.com/2017/04/why-art-direction-is-critical-to-responsive-design/)
* Do a fallback when using next-gen formats such as webp
* Create a thumbnail or preview image \(or both!\)

Read an amazing [Image Guide](https://images.guide/) by Addy Osmani.

#### Optimization Tools

* [ImageOptim](https://imageoptim.com) software with nice GUI
* mozjpeg, jpegtran, pngquant, optipng, svgo, webp optimization libraries, from the terminal or in a pre-commit hook
* [imagemin](https://web.dev/use-imagemin-to-compress-images) combining above mentioned libraries with its plugin system. library for usage
* [image-webpack-plugin](https://www.npmjs.com/package/image-webpack-loader)
* [Cloudinary](https://cloudinary.com)as a third-party solution with cool AI underneath

Danny compared how each tool perform: [https://github.com/dannytce/image-optimization](https://github.com/dannytce/image-optimization)

[The comprehensive article by Addy Osmani](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/automating-image-optimization/) on Google Developers.

#### When to optimize?

All the time! You shouldn’t work with unoptimized assets, because it slows down your machine. Also if you are optimizing your assets during the build time. You actually need to preview those optimized images, to confirm if they were optimized properly. It’s not bad and perfectly suitable for image uploading from the app itself. But the rest of the images which are part of designs should be optimized right away.

There are three main times when you can optimize:

**Runtime of application**

* Services like [Cloudinary](https://cloudinary.com/) provide an amazing experience of working with images
* Unfortunately with a big amount of images you are also paying a lot of money
* There are cheaper alternatives, but why to pay anything, when you do need to. Cloudinary is a great service, but you need to use it all the time.

**Build time**

* Not ideal, because you are working with unoptimized assets, which slows your machine. And you are not seeing the final result until build step
* Affects a build time \(Optimization itself is a very expensive process, thus it’s slow\)
* With each build, you need to run optimization again. This seems to be contra-productive.
* Usually, we build our apps with a webpack, which is a bundler. it shouldn't do the optimization in a first-place.

**Development time**

* Whenever you are adding new images to your project, optimize them!
* Whenever you are exporting images from a design editor, be sure you are exporting an optimized version. For Sketch, you use an amazing ImageOptim extension, which is running in the background and does the optimization automatically.

### Videos

If you need to display videos and don't want to embed them from services like YouTube, or Vimeo because you want more control over your player and its controls, then the HTML5 video tag is your solution. It works with a few file formats - MP4the oldest and most popular, WebMand Ogg more forward-thinking, but not so good browser support.

You may also want to give some extra life to your homepage by adding video backgrounds. This can provide great visual effects but comes with the cost of megabytes, so if you decide to pay the price, use short, well-compressed files, and always consider using a fallback for mobile devices.

Even though it’s become possible to autoplay background videos on mobile phones, you need to think of which internet network is mobile phone using. It could be a fast WiFi, or maybe a 3G.

Unfortunately, based on [caniuse.com](https://caniuse.com/#feat=netinfo)there is still very vague support of Network Information API. You can write your own detection or maybe even put it into WebWorkers. But this matters just in case you really need to display a large image or a video.

### Fonts

There are a lot of ways to serve fonts for your website, but it's not always clear when to use which.

In most cases you'll be safe with [Google Fonts](https://fonts.google.com), given they have many fonts available for free, it's easy to use and won't give you the headache from setting up self-hosting, however, sometimes you're stuck with self-hosting because you have to use a font that is not provided by Google Fonts. No matter which method you choose always think of subsetting \(Google Fonts support this\), as you probably won't need the full font set that might contain characters from specific aphlabets \(eg. greek\), and you don't want unused stuff to be loaded in your user's browser. [Be careful not to overuse it though.](https://www.bramstein.com/writing/web-font-anti-patterns-subsetting.html)

#### Font loaded detection

CSS property font-display[got a very solid cross-browser support](https://caniuse.com/#feat=css-font-rendering-controls%26search=font-display). And it’s also supported by Google Fonts.

But if you would love to have bigger control, you will probably also want to use [Font Face Observer](https://fontfaceobserver.com). It's an amazing, lightweight tool to detect if a font has already loaded on your website, it works with font services, and self-hosted fonts as well, the Promise based API is straightforward, and the browser support is very good. Here's a simple usage which resolves [FOUT](bundle-size.md#fout-foit-foft)for My Family font.

```javascript
const font = new FontFaceObserver('My Family')

font.load().then(function() {
  document.documentElement.className += ' fonts-loaded'
})
```

```css
.fonts-loaded body {
  font-family: My Family, sans-serif;
}
```

#### Naming

If you are having the same font with different types \(let's say Roboto-Regular, Roboto-Bold, Roboto-Italic\) always use the same font-family in CSS, but change the font with font-weight/font-style properties:

```css
@font-face {
  font-family: 'Roboto';
  src: url('Roboto-regular-webfont.woff2') format('woff2'), url('Roboto-regular-webfont.woff')
      format('woff');
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: 'Roboto';
  src: url('Roboto-bold-webfont.woff2') format('woff2'), url('Roboto-bold-webfont.woff')
      format('woff');
  font-weight: bold;
  font-style: normal;
}

@font-face {
  font-family: 'Roboto';
  src: url('Roboto-regular-italic-webfont.woff2') format('woff2'), url('Roboto-regular-italic-webfont.woff')
      format('woff');
  font-weight: normal;
  font-style: italic;
}
```

#### Font stacking

One more thing you have to keep in mind when dealing with fonts is font stacking, which is basically a no-cost backup and can come handy if for instance font files go missing, font services are down, or font downloading is disabled in the browser. \(yes, that happens sometimes\)

#### FOUT, FOIT, FOFT

Flash of Unstyled Text \(FOUT\), Flash of Invisible Text \(FOIT\) and Flash of Faux Text \(FOFT\) are very unpleasant from the UX perspective. As a frontend developer you are the last person who can prevent it. Use font-display or load fonts asynchronously.

### AWS S3 storage

Amazon Simple Storage Service is a storage service suitable for scaling. You can upload there as many files as you need. And almost for free. Usually, it’s a task for backend developers. But if you are building a CMS, or you just have too many large files in your repository, consider moving them to the AWS S3.

To maximize the performance, use it with [CDN](deployment.md#content-delivery-network-cdn) \(for example Amazon CloudFront\)

## Code splitting

Usually, web apps have different pages with different features. It doesn't make sense to load all of them since just a small chuck is used. A common practice is to split your code into smaller pieces or chunks either by feature or route.

This decreases an initial load of the web a lot because we serve just a small portion of the needed code to the end-user.

### How to do a code-splitting?

Next.js and Gatsby are doing this automatically by files in pagesfolder. The output is route based chunks.

When you need to do even more chunks, you can leverage also a [dynamic import](https://webpack.js.org/guides/code-splitting/)feature of webpack. The feature itself is the [ECMAScript proposal](https://github.com/tc39/proposal-dynamic-import), which is not accepted yet. But you can fully use it with webpack!

[React.lazy](https://reactjs.org/docs/code-splitting.html#reactlazy)is allowing you to use dynamic import as a component when [React.Suspense](https://reactjs.org/docs/code-splitting.html#suspense) renders fallback \(like Loading component\) when the component is not fully fetched.

To verify how did you perform code-splitting, use [Chrome's Coverage tab](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage)and [Webpack Bundle Analyzer](https://github.com/webpack-contrib/webpack-bundle-analyzer) to verify your chunks.

## http/2

\[TODO\]

## 3rd party libraries

When it comes to frontend development we are usually relying on many 3rd party libraries.

* Some of the 3rd party libraries could be grouped into common chunks, or even loaded from CDN
* Some libraries are too big, always check their size. And also think whether their usage is really needed for a project.
* Besides their size, you should also check their stability\(e.g. is that even production-ready\) and security.

## Forbidden libraries

We work with React and many other great libraries in the ecosystem. But instead of writing down what exactly our technological stack is, it’s much easier to point out what we don’t recommend to use.

### Bootstrap, Material UI

Any UI library is great and doing its perfect job. But when you are dealing with numerous projects build with different styles it’s actually really hard to master all of these. And choosing one specific is bounding your hands for the future scalability.

Also, when you are implementing very custom designs, usually these don’t match with predefined styles of UI libraries. So, in the end, you need to rewrite them. And maybe it’s easier just to write it from scratch.

Of course, there are exceptions. For example, when you are building an administration and really do not care about design. Actually the opposite, you would like to use anything battle-tested.

React-admin is a great example of a solid administration using Material UI.

### jQuery

The era of jQuery with all of the SPA frameworks is getting down. It used to be great and still has some use cases. But what you can do with jQuery you can also do with React or Vanilla JavaScript. So why worry about another big dependency. Also, the DOM manipulation doesn’t work well with React.

There are many great jQuery plugins and libraries. But unfortunately, they are quite heavy considering again jQuery as a big dependency.

### Redux-form

We already have our form favorite - Formik. But it doesn’t mean that it’s the best option. There are many great alternatives. Unfortunately, redux-form is not one of them. Even though it’s quite popular and has a lot of stars on GitHub, it has one critical issue. It manages the state of form in Redux. Which leads to bad performance.

The author of the library already created a new - React Final Form. This is yet another sign, why you should avoid redux-form for your project.

### Moment.js

Dealing with date in JavaScript is difficult. Especially when it comes to timezones. Moment.js is without any doubt a great library with amazing API. Given its large size, it’s suitable just for Node.js projects. On the web, you should go for a smaller alternative such as [data-fns](https://github.com/date-fns/date-fns) or [day-js](https://github.com/iamkun/dayjs) which is only 2kB small.

[https://github.com/you-dont-need/You-Dont-Need-Momentjs](https://github.com/you-dont-need/You-Dont-Need-Momentjs)

### Think before you npm-install

This is a generic rule you can apply for any other library. Always consider its size by using [BundlePhobia](http://bundlephobia.com), Wix’s [Import Cost](https://marketplace.visualstudio.com/items?itemName=wix.vscode-import-cost)plugin for VSCode or using the [webpack-bundle-analyzer](https://github.com/webpack-contrib/webpack-bundle-analyzer).

Also, think of [security](https://github.com/strvcom/frontend/tree/11faa047391814857bf86cdb62b9fb815731f911/project-guidelines/effective-and-consistent-workflow/dependency-checking/README.md#security).

