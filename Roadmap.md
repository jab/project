# Roadmap

An overview of what the core Polymer team is looking to work on over the next few months.

As a caveat - this is a living doc, and will evolve as priorities grow and shift. The Polymer project will always be adapting to new use-cases and evolutions in the platform - this roadmap is more of a "North Star" of what we're looking to work on than a strict timeline.

Please feel free to file issues on this repository if you have questions, concerns, or suggestions.

### Polymer 2.0

We are hard at work iterating on the next major version of Polymer.

For details on the goals of 2.0 and the most recent state, check out the [announcement blog post](https://www.polymer-project.org/1.0/blog/2016-09-09-polymer-2.0.html) and the [repository branch](https://github.com/polymer/polymer/tree/2.0-preview).

*Recently Shipped*:

- Polymer 2.0 [preview branch](https://github.com/polymer/polymer/tree/2.0-preview)

*Goals*:

- Make the Polymer library compatible with latest web component specs and shipping implementations.
  - Update styling system to be compatible with custom properties.
  - Update shady DOM to be compatible with shadow dom v1.
  - Update custom elements treatment to be compatible with custom elements v1.
- Provide a smooth migration from Polymer 1.x.
  - Provide backwards-compatibility layer that re-creates the `Polymer({})` factory from 1.x.
  - Provide an upgrade tool for doing mechanical conversions to elements.
  - Design a "hybrid mode" so that elements built in a certain way can run under 1.x or 2.0.
- Eliminate leaky abstractions.
  - Remove `Polymer.dom` API.
  - Remove the `set/notifyPath` API's.
- Support ES6 class-based syntax as primary way to build new elements.
  - `class MyElement extends Polymer.Element` !!
- Improve factoring for more flexible usage.
  - Break out "Shady DOM" shim from Polymer.
  - Break out CSS property shim from Polymer.

### Building Applications with Polymer  

We see [Progressive Web Apps](https://developers.google.com/web/progressive-web-apps?hl=en) as a big part of the future of the web - web applications that take ["all the right vitamins"](https://infrequently.org/2015/06/progressive-apps-escaping-tabs-without-losing-our-soul/) to be added to a user's homescreen, work while the user is offline, send a user push notifications, and more. Many of these types of features that [Service Worker](http://www.html5rocks.com/en/tutorials/service-worker/introduction/) provides also marry extremely well with a component-driven, tight-to-the-platform development model supported by Web Components. We want to publish more around how we see these pieces playing together - how to build on the web platform the way it is intended - and also provide a suite of tools to actually manifest these ideas.

Moreover, we want to be thinking more about how to manage data flow within large applications built out of web components. We will be exploring how popular patterns like Flux work in a web components world.

*Recently Shipped*:

- [Polymer App Toolbox](https://www.polymer-project.org/1.0/toolbox/) - a set of tools and components useful for building full-fledged Progressive Web Apps. We'll continue to publish new content, demos, and components to make this an even more effective way to build on the modern web.

*Goals*:

- Continue to add power and functionality to the Polymer App Toolbox and Polymer CLI.
- Build additional end-to-end demos like the [Shop](https://shop.polymer-project.org/) progressive web app for different verticals.

### Element Porting, Maintenance, and Performance

Much of the core Polymer team's time is spent fixing issues on existing Polymer elements. We're incredibly eager to push forward with new elements to solve new problems, but need to get a handle on the existing maintenance burden. We're approaching this from multiple angles - continually improving quality and fixing bugs, improving the core Polymer team's tools and systems for maintenance, and aiming to be better contributors to the open web components ecosystem.

We're extremely bullish about this growing web component ecosystem, and excited to help it grow in any way we can.

*Goals*:

- Port the 1.x-based elements built by the Polymer team to the 2.0-compatible "hybrid mode," to make it easy for teams relying on these components to upgrade.
- Reduce and achieve sustainable element maintenance costs.
  - Help promote community-driven elements and bring in additional maintainers from the community.
  - Increase number of merged community Pull Requests to elements by 100%.
  - Keep time-to-triage for incoming element issues < 5 days.

We're also always looking for opportunities to improve element performance. We'll particularly be taking a hard look at elements that may be used many times on a single page - things like [paper-input](https://elements.polymer-project.org/elements/paper-input) and [iron-icon](https://elements.polymer-project.org/elements/iron-icon) - to make them as fast and lightweight as possible.

*Goals*:

- Improve our offering of high-performance elements.
  - Identify high-use elements and ship ultra-lightweight versions.
  - Iterate on and share element performance measurement techniques and benchmarks.

### Tooling

The Polymer team works on [a](https://github.com/PolymerLabs/polyserve) [lot](https://github.com/Polymer/vulcanize) [of](https://github.com/PolymerLabs/polygit) [tools](https://github.com/PolymerLabs/crisper) to improve the development workflow and enable fast deployed sites. Many of these [tools](https://www.polymer-project.org/1.0/tools/overview.html) can get lost or buried, and it can be complicated to figure out how they might work together.

We want to keep all of the tools modular, but for simplicity and better discovery we're exploring building a wrapped-up "Polymer CLI," that includes the tools we build for Polymer development. Currently we're focusing only on Polymer-specific tools - for things like package management we want to continue to rely on the most commonly-used tools in the broader ecosystem that fit the development model.

*Recently Shipped*:

The [Polymer CLI](https://github.com/polymer/polymer-cli) pulls together a number of useful tools, and makes it easy to get started building a web component or web components-based application.

*Goals*:

- Rationalize our tools offering and improve code quality.
  - Refactor all tools around new, fast, flexible static analyzer.
  - Rename tools to make it easier to know what they do.
- Launch 1.0 of the Polymer CLI.
  - First-class support for more varied project structures.
  - Refactored around new static analyzer.
- Improve support for NPM.


### Community and Ecosystem

The Polymer community has grown incredibly quickly and there are a number of individuals making extremely meaningful contributions to both the library and Polymer elements. We want to do more to highlight community work and generally better serve the Polymer and web components ecosystem. This means even more transparency around the core Polymer team's roadmap, more regular announcement and updates, and promoting element ownership beyond just the core Polymer team.

*Goals*:

- Accelerate Polymer + Community engagement.
  - Tighten the core Polymer team and community feedback loop - better evolve Polymer as the community evolves.
  - Publish all elements to npm and bower.
  - Regularly publish project and roadmap updates.
  - Work with community members to help drive elements forward.
  - Use [Polycasts](https://www.youtube.com/playlist?list=PLOU2XLYxmsII5c3Mgw6fNYCzaWrsM3sMN) to highlight awesome elements being built.


