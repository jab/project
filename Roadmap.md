# Roadmap

An overview of what the core Polymer team is looking to work on over the next few months.

As a caveat - this is a living doc, and will evolve as priorities grow and shift. The Polymer project will always be adapting to new use-cases and evolutions in the platform - this roadmap is more of a "North Star" of what we're looking to work on than a strict timeline.

Please feel free to file issues on this repository if you have questions, concerns, or suggestions.

Last Updated: 5/7/2018 by graynorton

## Polymer 3.0

Polymer 3.0 (released May, 2018) represents a simple but important step forward from Polymer 2.x: we've moved from HTML Imports to ES Modules, and from Bower to npm.

These changes represent a move toward the mainstream, making it easier to use Polymer (and Polymer-based elements) with other popular libraries, frameworks and tools. As we'll discuss below, they also provide a solid foundation for future enhancements.

Like we did for the Polymer 1.x-to-2.0 transition, we made a smooth upgrade path our top priority for Polymer 3.0. Polymer's API remains almost unchanged, and we've provided an upgrade tool ([polymer-modulizer](https://github.com/Polymer/polymer-modulizer)) that will automatically handle most of the work in converting your 2.x-based elements and apps to 3.0.

With the 3.0 release, we've updated not just the core Polymer library, but all of the various resources we provide for building elements and apps with web components:

*   The Polymer Elements, like the core library, have been been converted to ES Modules and distributed via npm.
*   The Polymer CLI and associated tools have been updated to support developing, testing and deploying projects composed of ES Modules.
*   The Polymer Starter Kit and other app and element templates included with the CLI have been converted to use modules.
*   We've provided a new loader for the v1 web components polyfills, since the loader previous loader assumed the use of HTML Imports.
*   The element catalog at webcomponents.org will be updated to support elements built with modules and distributed via npm.
*   We've updated our documentation to reflect all of these changes.

> In sum, the goal of Polymer 3.0 is to make sure that anyone who has built elements and apps with earlier versions of Polymer (or following patterns and conventions established by Polymer) can easily move forward with us as we start a new chapter.


## What's next?

So, what will that new chapter hold? We see a few major themes...

First, **we see web components becoming increasingly mainstream**—they'll be natively supported in three of the four major browsers by year's end and are enjoying unprecedented support from other libraries, frameworks and tools. We'll keep working to eliminate barriers to adoption, as exemplified by our current effort to help the web components ecosystem move to ES Modules and npm.

At the same time, **we see our own offerings becoming lighter and more loosely coupled**. Since day one, our guiding vision has been: make it simpler to develop web components, while adding minimal weight. Along the way, we've made compromises, increasing the size and scope of the library in the interest of performance or developer productivity. Our next offerings will swing back toward that guiding vision.

Finally, with the core web components standards firmly established, **we see opportunities to help shape and advocate for a new generation of related standards**—standards that will bring improvements to styling and theming, templating, and loading, among other things.

Let's take a closer look at how these themes will manifest in our roadmap. There are still some open questions—names and details are subject to change—but the sections below should give you a good idea of where we're headed.


### Libraries

In Polymer 2.0, we did some significant refactoring, decomposing the core library into a set of layered mixins. While it's still easy to adopt the library as a whole, developers can now define lighter-weight base classes incorporating only the layers they need.

With Polymer 3.0 now released, we'll be proceeding further down this path toward smaller and more loosely coupled units of functionality. Specifically, we'll:

*   Ship a tiny new foundation library, focused solely on streamlining the management of an element's properties and attributes. It won't offer any functionality for creating and updating DOM; rather, it's intended to be paired with an opinionated rendering or templating system.
*   Pair this new foundation library with [lit-html](https://github.com/Polymer/lit-html) (the standalone templating library we introduced last year) to provide an ultra-light, highly performant base class (currently previewed as [LitElement](https://github.com/PolymerLabs/lit-element)) with a simple but expressive API. With lit-html and LitElement headed for 1.0 releases in the coming months, LitElement is our recommended base class for new development.
*   Maintain the full Polymer 3.x API surface (including the templating and data system from Polymer 1.x - 3.x) in a separate library, built on the same new foundation. We won't do new feature development on this "classic" library, but we'll provide maintenance releases to meet the needs of existing apps and elements. We'll also offer guidance and support for developers who want to migrate apps and elements from the classic base classes to LitElement—see the [FAQ](#faq) for more on this.


### App toolbox

Along with these changes to our library lineup, we'll be revamping our toolbox for building apps and relaunching it as [PWA Starter Kit](https://github.com/Polymer/pwa-starter-kit).

If you've followed the last two Polymer Summits or engaged with us online, you'll know that we've become strong proponents of unidirectional data flow and centralized state management for applications. PWA Starter Kit will provide out-of-the-box support for this model, incorporating the popular [Redux](https://redux.js.org/) library, integrating it simply and cleanly with a web components view layer based on LitElement, and making it easy to factor your Redux code for efficient loading via the [PRPL pattern](https://developers.google.com/web/fundamentals/performance/prpl-pattern/).

PWA Starter Kit will also feature updated samples, templates, and an all-new set of docs. Like LitElement, PWA Starter Kit is still in development, but it's available to try out today and rapidly firming into shape.


### Elements

A few months ago, we blogged about our [future plans for elements](https://www.polymer-project.org/blog/2017-11-27-future-of-elements.html)—specifically, why we weren't updating the existing Polymer Elements to canonical, class-based Polymer 2.0 syntax, and what we intended to do instead.

In short, our elements were overdue for a rewrite, and it made more sense for us to invest our limited resources in a next-generation element set. That's still true today, but our plans have evolved and we can provide a bit more detail.

To replace our current paper-elements collection, we'll be collaborating with Google's Material Design Components team, whose charter is to provide performant, spec-compliant implementations of Material Design components for multiple platforms. By leveraging their base web implementation, we believe we'll be able to offer developers a better product—an actively maintained set of [Material Web Components](https://github.com/material-components/material-components-web-components) that closely tracks the Material Design spec.

Beyond the Material Web Components, we'll scale back significantly on our own element lineup. We'll continue to develop a small set of elements (including components for responsive layout and infinite lists), but in the spirit of teaching developers to fish, we'll turn more of our attention toward documenting best practices for building and distributing reusable elements.

To ensure exposure and distribution for the growing catalog of community-built elements, we'll continue to maintain and invest in [webcomponents.org](https://www.webcomponents.org/).


### Tools

We've come to a crossroads with respect to our tools efforts, and we're not yet sure which direction we'll go from here.

With our move from HTML Imports to ES Modules, much of the historical need for maintaining our own toolchain has melted away; it will now be easy to use our offerings with popular third-party tools like Webpack and Rollup.

But with our tools updated to support ES Modules, they work for a much broader range of projects, including projects that don't use our libraries or elements. While we respect and appreciate today's mainstream tools, we'd also like to see our platform-centric approach to web tools adopted more widely.

In the coming months we'll be thoughtfully weighing our options for tools in the post-Polymer-3.0 era, and we'll welcome your input as we do so.


### Polyfills

The Polymer team has long been responsible for producing web components polyfills: designing and developing them, optimizing their performance, and updating them as the specs evolve and browser support progresses.


We look forward to a day in the not-too-distant future when the core web components polyfills become obsolete; until then, we'll continue maintaining them. Where applicable, we'll also develop polyfills (and/or tool support) for the new standards we invest in.


### Standards

In addition to our ongoing product development work, we are helping to define and/or advocating for a number of emerging standards. We believe each of these has the potential to push the web platform and ecosystem forward in ways that benefit users and developers alike.



*   **CSS Shadow Parts** ([draft spec](https://drafts.csswg.org/css-shadow-parts/), [explainer](https://meowni.ca/posts/part-theme-explainer/)) will make it easier to style and theme web components—see Monica's explainer to learn more.
*   **Scoped Custom Element Registries** ([proposal](https://github.com/w3c/webcomponents/issues/716)) would allow a custom element definition to be scoped to a subset of the DOM tree, rather than apply to the page's global scope. This would help to avoid conflicts in larger apps.
*   **HTML Template Instantiation** ([proposal](https://github.com/w3c/webcomponents/blob/gh-pages/proposals/Template-Instantiation.md), [discussion](https://github.com/w3c/webcomponents/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+%22%5BTemplate+Instantiation%5D%22)) aims to provide enhanced built-in support for creating and dynamically updating instances of HTML Templates. The proposal's central concepts are shared by lit-html, which was written in anticipation of such a feature, and we've been working actively to help refine and advance the proposal.
*   **HTML Modules** ([proposal](https://github.com/w3c/webcomponents/issues/645#issuecomment-343601237), [discussion](https://github.com/w3c/webcomponents/issues?q=is%3Aissue+is%3Aopen+html+modules+label%3Amodules)) would provide native support for loading modular HTML content—much as HTML Imports did, but in a manner that would integrate seamlessly with ES Modules.
*   **Package Name Maps** ([proposal](https://github.com/domenic/package-name-maps), [discussion](https://github.com/domenic/package-name-maps/issues)) would enable the browser's native module loader to import ES Modules specified by package name (e.g. `import LitElement from lit-element;`). This pattern is dominant in today's JavaScript package ecosystem, but modules written this way can't currently be loaded in the browser unless bundled or rewritten to replace package-name specifiers with full paths.

<a id="faq"></a>
# FAQ

### Polymer 3.0 or LitElement?

<b class="qa">Q:</b> <i>I'm starting a new project. Should I use Polymer 3.0 or LitElement?</i>

<b class="qa">A:</b> For new projects, we suggest that you use LitElement (and if your project is an app, PWA Starter Kit, which incorporates LitElement).

While lit-html, LitElement and PWA Starter Kit are still in development, they're on the fast track to 1.0 releases, and they represent the future direction of the Polymer project.

If your project has a short development cycle and you're uncomfortable with including pre-release dependencies in your production deployments, you might choose to use Polymer 3.0 instead. This is a safe choice, as we'll continue to support the Polymer 3.x APIs with maintenance releases for the foreseeable future.


### Should I update to Polymer 3.0?

<b class="qa">Q:</b> <i>Should I update my existing app or element to use Polymer 3.0?</i>

<b class="qa">A:</b> Yes, we recommend that you update existing apps and elements to use Polymer 3.0. Doing so will open up a world of mainstream libraries and development tools for you to choose from, and publishing your reusable elements to npm will greatly increase the size of your potential user base.

The upgrade process is mechanical, and polymer-modulizer can do most of the work for you. Once you've updated to Polymer 3.0 (and adopted ES Modules and npm), you can migrate to LitElement as your needs dictate, and at your own pace (see the next question).

Exceptions to this rule might be small projects that can easily be reimplemented using LitElement (skipping Polymer 3.0), or large projects that are no longer being actively developed (which you may choose to leave on Polymer 2.x). 


### How do I upgrade to LitElement?

<b class="qa">Q:</b> <i>What is the upgrade path from Polymer 1.x - 3.x to LitElement?</i>

<b class="qa">A:</b> Unlike the migration from Polymer 2.x to Polymer 3.0, the path to adopting LitElement is not formulaic – it will depend on how your element or app is currently implemented.

That said, it's not necessarily hard. First, thanks to the inherent interoperability of web components, you can upgrade your app or element collection one piece at a time; elements you've built with or upgraded to LitElement can sit alongside and interact with elements you've built using previous versions of the Polymer library.

Elements and apps you've built following the basic precepts of unidirectional data flow (e.g., data flowing from above via one-way bindings) should also be straightforward (though not mechanical) to migrate.

The biggest migration challenges will be for apps that have leaned heavily on two-way bindings, distributing app logic and responsibility for data mutations across many components. Apps like these will need to be rethought with unidirectional data flow in mind.

As we move LitElement out of preview and toward a 1.0 release, we'll provide more guidance and support for developers migrating from Polymer 1.x - 3.x.


### Dependencies not in ES modules/npm?

<b class="qa">Q:</b> <i>I want to adopt Polymer 3.0 or LitElement, but my app depends on third-party web components that haven't yet moved to ES Modules and npm. What do I do?</i>

<b class="qa">A:</b> Contact the developers of your dependencies and let them know that you'd like them to make their web components available as ES Modules in packages on npm. Developers of many popular web components have already begun doing so; notably, the latest versions of Vaadin's core components are already [available on npm](https://www.npmjs.com/search?q=%40vaadin).

If you use third-party components whose authors are unresponsive or aren't planning to update, you have a couple of choices: you can replace these components with alternatives, or you can fork them and update them yourself (using polymer-modulizer).


### Dependencies not compatible with the native module loader?

<b class="qa">Q:</b> <i>I want my ES Module-based app to utilize the browser's native module loader, but some of the npm packages I'd like to use aren't distributed in a form that's compatible with the native loader. What do I do?</i>

<b class="qa">A:</b> With ES Module support having landed in all of the major browsers and coming to node.js, the proportion of npm packages distributed in browser-loadable ES Module form is growing. We're working actively to promote this practice, with our contribution to the Package Name Map proposal being one example. You can expect us to talk more about this going forward.

That said, many npm packages that might be useful in the browser are still distributed such that they can't be loaded directly in the browser – they may be in the older CommonJS format, or they may use future JavaScript features that aren't yet supported in browsers. If you want to use such a package, we encourage you to file an issue for the package author, asking that they support the browser's native module loader.

Meanwhile, the easiest way to use these packages today is to use a tool like Webpack or Rollup that can bundle heterogeneous modules and compile out unsupported language features as needed.

### What about declarative HTML templates?

<b class="qa">Q:</b> <i>I like writing templates using declarative HTML syntax. What do I do?</i>

<b class="qa">A:</b> This question has a near-term answer and a longer-term answer.

For the near term, Polymer 3.0 still supports exactly the same declarative template syntax as Polymer 1.x and 2.x (albeit within JavaScript template literals). So will the "classic" library that we'll release and maintain post-3.0, so you can continue writing templates this way if you like, with the important caveat that this codebase won't see active development going forward.

For the longer term, we aren't giving up on the promise of declarative HTML templates. Our work on the HTML Modules spec reflects this, as does our choice to factor our lowest-common-denominator base class into a standalone library that doesn't have an opinion on templating. It's too early to say anything concrete, but we can imagine a future in which we offer a new alternative to LitElement that opts for declarative HTML templates.

Further, the HTML Template Instantiation proposal is well suited to provide native support for both JavaScript-based templating approaches (like lit-html) and purely declarative HTML-based approaches. We're keeping both in mind as we work to advance the proposal.


### What about .html files?

<b class="qa">Q:</b> <i>I like declarative HTML templates AND I want to keep writing them in .html files. What do I do?</i>

<b class="qa">A:</b> This one also has two answers.

For the near term, we'll provide guidance and support for developers who want to write templates in .html files for use with Polymer 3.0 and the forthcoming "classic" library. The approach we have in mind will require the use of at least lightweight tools during development, which means that won't be able to run your element or app source directly in the browser if you opt to write your templates in .html files.

Longer term, the HTML Modules proposal aims to provide a tool-free solution for the declarative HTML template use case.


### Why not wait for HTML Modules?

<b class="qa">Q:</b> <i>Why don't you keep using HTML Imports until HTML Modules or another suitable replacement is available?</i>

<b class="qa">A:</b> With Custom Elements, Shadow DOM and HTML Templates all reaching critical mass in terms of browser support and web components enjoying a surge of interest, we believe the best thing we can do to bolster future prospects is to remove remaining barriers to adoption.

Sadly, HTML Imports had become the largest such barrier, requiring the continued use of polyfills in browsers that otherwise no longer required any, dictating the use of specialized build tools and making it difficult to distribute reusable elements in a form that mainstream developers could easily consume.

These problems are solved by moving to ES Modules while we continue working through the standards process to land first-class native support for loading modular HTML.


### Can I keep using the Polymer data system?

<b class="qa">Q:</b> <i>I like Polymer's data system, with features like observers, computed properties and two-way bindings. What do I do?</i>

<b class="qa">A:</b> Like the "classic" declarative template syntax, these are features that you can continue using, provided you understand that they won't see active development going forward.

That said, we strongly encourage you to adopt LitElement and its simpler approach to data-driven views, based on unidirectional data flow and the functional mapping of application state to UI.

The Polymer data system was the spiritual successor to a would-be spec called Model Driven Views (MDV). Based on concepts that were popular in user-space frameworks and libraries at the time, MDV was conceived along with the core web components specs, recognizing that the low-level primitives supplied by the core specs didn't provide an ergonomic, out-of-the-box way to bind data to views.

When work on MDV was halted to focus on landing the core web components specs, its functionality was pulled into the Polymer library. While the Polymer data system has proven to be powerful and performant, it has undoubtedly added significant complexity and weight to the library. When not used carefully, it has also contributed to frustrating complexity in developers' elements and apps.

In all, we don't believe that the virtues of the Polymer data system continue to justify its size and complexity, especially given our guiding vision of providing solutions that are light and close to the platform.
