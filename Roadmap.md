# Roadmap

Here’s an overview of what the Polymer team is looking to work on over the next few months.

This is a living doc that will evolve as priorities grow and shift. Please feel free to file issues on this repository
if you have questions, concerns, or suggestions.

Last Updated: 9/3/2019 by graynorton

## What we're working on...

* **[Material Web Components](https://github.com/material-components/material-components-web-components) (MWC):** We're
  actively driving MWC toward release-readiness, focusing on:
  * Reaching feature parity with the underlying [MDC-Web](https://github.com/material-components/material-components-web)
    CSS and JavaScript
  * Fleshing out documentation
  * Adding tests and fixing bugs
  
  We expect to reach our goals in these areas within Q4 2019 but aren't yet projecting a production release date because,
  to meet requirements for internal use at Google, we continue to explore some changes that may affect APIs and usage
  patterns.

* **Server-side rendering (SSR):** We're doing R&D on server-side rendering for lit-html and LitElement, with support
  for lazy, incremental, client-side hydration. This includes work on a node.js-based server and work in the libraries
  themselves. While we're targeting lit-html and LitElement first, we're designing the solution with support for
  alternative renderers and Web Component base classes in mind. We've made significant progress, but it's too early
  to say exactly how and when this work will be released.

* **Libraries and polyfills:** We're actively developing [lit-html](https://lit-html.polymer-project.org),
  [LitElement](https://lit-element.polymer-project.org) and the
  [Web Components polyfills](https://github.com/WebComponents/webcomponentsjs): fixing bugs, making incremental
  improvements, adding support for new platform features as they emerge, reviewing community PRs, and cutting releases
  when features and fixes land.
  
  We're also working toward an initial release of
  [lit-virtualizer](https://github.com/PolymerLabs/uni-virtualizer/tree/master/packages/lit-virtualizer), a library adding
  support for virtual lists, virtual scrollers and similar use cases to lit-html and LitElement.
  
  Finally, we're continuing to maintain the original Polymer library and Polymer Elements,
  making critical fixes on an as-needed basis.

* **Standards:** We continue to be involved in the standards process. Now that the original Web Components specs have
  landed in all of the major browsers (pending the upcoming release of Chromium-based Edge), we are focused on a handful
  of new standards designed to improve Web Components' capabilities and developer experience. Our immediate priorities
  include [CSS Modules](https://github.com/w3c/webcomponents/blob/gh-pages/proposals/css-modules-v1-explainer.md),
  [CSS Shadow Parts](https://drafts.csswg.org/css-shadow-parts/) (including `::theme`) and
  [Scoped Custom Element Registries](https://github.com/w3c/webcomponents/issues/716).

* **Tools:** With HTML Imports deprecated and our current libraries having adopted JavaScript Modules, mainstream tools like
  [Rollup](https://rollupjs.org/guide/en/) and Webpack now work well for Web Components projects. We have therefore decided
  not to make further investments in the Polymer CLI and underlying tools, and we encourage developers to migrate to
  alternative toolchains. [open-wc](https://open-wc.org) is a great place to start.
  
  We will continue to do some targeted tools work where it’s of strategic value, generally in the form of extensions or
  contributions to existing tools. We’re currently focused on testing and developer experience improvements: more seamless
  testing of web components with Karma, and more widespread support for syntax highlighting and advanced code editing features
  within JavaScript tagged template literals. Future plans include support for hot module reloading during development and a
  new, library-agnostic documentation system for web components.
  
Notably absent from our active work is [PWA Starter Kit](https://pwa-starter-kit.polymer-project.org/). This project is on
hold pending our ongoing SSR efforts, which are of higher priority. We expect our SSR solution to have a significant impact
on our recommended patterns and practices for building apps with Web Components and plan to revisit our offerings in the
end-to-end app development space once SSR is further along.
