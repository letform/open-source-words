react-howto If youre new to React (or frontend in general) you may find the ecosystem confusing. There are a few reasons for this. React has historically been targeted at early-adopters and experts Facebook only open-sources what it actually uses, so it doesnt focus on tooling for smaller-than-Facebook projects Theres a lot of bad marketing masquerading as React guides Throughout this document, Ill assume youve built a web page with HTML, CSS and JavaScript. Why should you listen to me? Theres a ton of conflicting advice about React out there; why listen to me? I was one of the original members of the Facebook team that built and open-sourced React. Im no longer at Facebook and Im now at a small startup, so I have a non-Facebook perspective as well. How to tackle the React ecosystem All software is built on a stack of technologies, and you need to understand enough of that stack to build your app. The reason why the React ecosystem of tooling seems overwhelming is because its always explained in the wrong order. You should learn, in this order, without skipping ahead or learning concurrently: React itself npm JavaScript “bundlers” ES6 Routing Flux You dont need to learn all of these to be productive with React. Only move to the next step if you have a problem that needs to be solved. Additionally, there are a few topics that are often mentioned in the React community that are "bleeding edge". The topics below are interesting, but theyre difficult to understand, are far less popular than the above topics and arent required for most apps. Inline styles Server rendering Immutable.js Relay, Falcor, etc Learning React itself Its a common misconception that you need to waste a lot of time setting up tooling to start to learn React. In the official documentation youll find a copy-paste HTML template that you can save in an .html file and get started right away. No tooling is required for this step, and dont start learning extra tooling until youre comfortable with React basics. I still think the easiest way to learn React is the official tutorial. Learning npm npm is the Node.js package manager and is the most popular way front-end engineers and designers share JavaScript code. It includes a module system called CommonJS and lets you install command-line tools written in JavaScript. Read this post for background on why CommonJS is necessary for browsers, or the CommonJS Spec Wiki for more on the CommonJS API. Most reusable components, libraries and tools in the React ecosystem are available as CommonJS modules and are installed with npm. Learning JavaScript bundlers For a number of good technical reasons CommonJS modules (i.e. everything in npm) cannot be used natively in the browser. You need a JavaScript “bundler” to “bundle” these modules into .js files that you can include in your web page with a <script> tag. Examples of JavaScript bundlers include webpack and browserify. Both are good choices, but I prefer webpack since it has a lot of features that make development of large apps easier. Since its documentation can be confusing, I have a plug-and-play template for getting started and I wrote a how-to guide for webpack for more complex use cases. React also now offers an officially supported CLI tool called Create React App. It lets you create React projects powered by webpack without any configuration. It has its limitations, but it can serve as a great starting point, and its updates will add more features over time. It also offers an "ejection" feature that copies all configs and dependencies into your project so you have full control over them. One thing to keep in mind: CommonJS uses the require() function to import modules, so a lot of people get confused and think that it has something to do with a project called require.js. For a number of technical reasons, I would suggest that you avoid require.js. Its also not very popular in the React ecosystem. Learning ES6 Outside of JSX (which you learned in the React tutorial), you may see some funny syntax in React examples. This is called ES6, and its the latest version of JavaScript so you may not have learned it yet. Since its so new, its not supported in browsers yet, but your bundler can translate it for you with the proper configuration. If you just want to get things done with React, you can skip learning ES6, or try to pick it up along the way. You may see some talk about ES6 classes being the preferred way to create React components. This is untrue. Most people (including Facebook) are using React.createClass(). Learning routing “Single-page applications” are all the rage these days. These are web pages that load once, and when the user clicks on a link or a button, JavaScript running on the page updates the address bar, but the web page is not refreshed. Management of the address bar is done by something called a router. The most popular router in the React ecosystem is react-router. If youre building a single-page application, use it unless you have a good reason not to. Dont use a router if you arent building a single-page application. Most projects start out as smaller components inside of a larger application anyway. Learning Flux Youve probably heard of Flux. Theres a ton of misinformation about Flux out there. A lot of people sit down to build an app and want to define their data model, and they think they need to use Flux to do it. This is the wrong way to adopt Flux. Flux should only be added once many components have already been built. React components are arranged in a hierarchy. Most of the time, your data model also follows a hierarchy. In these situations Flux doesnt buy you much. Sometimes, however, your data model is not hierarchical. When your React components start to receive props that feel extraneous, or you have a small number of components starting to get very complex, then you might want to look into Flux. Youll know when you need Flux. If you arent sure if you need it, you dont need it. If you have decided to use Flux, the most popular and well-documented Flux library is Redux. There are a lot of alternatives out there, and youll be tempted to evaluate lots of them, but my advice is to just stick with the most popular one. Learning inline styles Pre-React, a lot of people reused CSS styles with complicated style sheets built by preprocessors like SASS. Since React makes writing reusable components easy, your stylesheets can be less complicated. Many in the community (including myself) are experimenting with getting rid of stylesheets altogether. This is a fairly crazy idea for a number of reasons. It makes media queries more difficult, and its possible that there are performance limitations using this technique. When starting out with React, just style things the way you normally would. Once youve got a feel for how React works, you can look at alternate techniques. One popular one is BEM. I recommend phasing out your CSS preprocessor, since React gives you a more powerful way to reuse styles (by reusing components) and your JavaScript bundler can generate more efficient stylesheets for you (I gave a talk about this at OSCON). With that said, React, like any other JavaScript library, will work just fine with a CSS preprocessor. Alternatively, you can also use CSS Modules, more specifically react-css-modules. With CSS Modules youll still write CSS (or SASS/LESS/Stylus), but you can manage and compose your CSS files like youd do with inline styles in React. And you dont need to worry about managing your class names using methodologies like BEM, as this will be handled for you under the hood by the module system. Learning server rendering Server rendering is often called "universal" or "isomorphic" JS. It means that you can take your React components and render them to static HTML on the server. This improves initial startup performance because the user does not need to wait for JS to download in order to see the initial UI, and React can re-use the server-rendered HTML so it doesnt need to generate it client-side. You need server rendering if you notice that your initial render is too slow or if you want to improve your search engine ranking. While its true that Google now indexes client-rendered content, as of January 2016 every time its been measured its been shown to negatively affect ranking, potentially because of the performance penalty of client-side rendering. Server rendering still requires a lot of tooling to get right. Since it transparently supports React components written without server rendering in mind, you should build your app first and worry about server rendering later. You wont need to rewrite all of your components to support it. Learning Immutable.js Immutable.js provides a set of data structures that can help to solve certain performance issues when building React apps. Its a great library, and youll probably use it a lot in your apps moving forward, but its completely unnecessary until you have an appreciation of the performance implications. Learning Relay, Falcor etc These are technologies that help you reduce the number of AJAX requests. Theyre still very cutting-edge, so if you dont have a problem with too many AJAX requests, you dont need Relay or Falcor.