# Roadmap

An overview of what the core Polymer team is looking to work on over the next few months.

As a caveat - this is a living doc, and will evolve as priorities grow and shift. The Polymer project will always be adapting to new use-cases and evolutions in the platform - this roadmap is more of a "North Star" of what we're looking to work on than a strict timeline.

Please feel free to file issues on this repository if you have questions, concerns, or suggestions.

Last Updated: 9/29/2017 by wmginsberg

### Polymer 3.0-preview
We announced an early sneak preview of Polymer 3.0 at [Polymer Summit 2017](https://www.youtube.com/watch?v=TDpiyrcOO30&list=PLNYkxOF6rcIDP0PqVaJxqNWwIgvoEPzJi). We then posted a two-part series on [what Polymer 3.0 entails](https://www.polymer-project.org/blog/2017-08-22-npm-modules.html) and [how to get started](https://www.polymer-project.org/blog/2017-08-23-hands-on-30-preview.html) with it. We've already posted all ~100 of our elements to npm. 

In summary: We're migrating to npm from Bower; migrating to ES Modules from HTML Imports; and not planning to change the API from Polymer 2.0. Because of that, the changes will be minimal and mechanical, so we built the Polymer Modulizer to automate the upgrade.  

Our current timeline for release is illustrated best on [this diagram](https://youtu.be/JH6jEcLxJEI?t=21m8s). Over the next couple months we plan to add more 3.0 support for Tooling and the Polymer CLI, as well as Polymer Elements. Towards the end of the year we will focus on Modulizer support for Polymer Applications. Throughout all of this we are rethinking our Docs site organization and approach to onboarding and education while developing new content.  

### Polymer 2.0

Polymer 2.0 was announced at [Google I/O 2017](https://www.youtube.com/watch?v=cuoZenpQveQ&t=981s). Along with our main keynote, we had 2 talks on [building elements](https://www.youtube.com/watch?v=assSM3rlvZ8&t=18s) with Polymer 2.0 and our [new tools](https://www.youtube.com/watch?v=tKvNeNGmOtU&t=96s). 

*Goals*:

- Make the Polymer library compatible with latest web component specs and shipping implementations.
  - ✔️ Update styling system to be compatible with custom properties.
  - ✔️ Update shady DOM to be compatible with shadow dom v1.
  - ✔️ Update custom elements treatment to be compatible with custom elements v1.
- Provide a smooth migration from Polymer 1.x.
  - ✔️ Provide backwards-compatibility layer that re-creates the `Polymer({})` factory from 1.x.
  - ✔️ Design a "hybrid mode" so that elements built in a certain way can run under 1.x or 2.0.
- Eliminate leaky abstractions.
  - ✔️ Remove `Polymer.dom` API.
  - ✔️ Remove the `set/notifyPath` API's.
- Support ES6 class-based syntax as primary way to build new elements.
  - ✔️ `class MyElement extends Polymer.Element` !!
- Improve factoring for more flexible usage.
  - ✔️ Break out "Shady DOM" shim from Polymer.
  - ✔️ Break out CSS property shim from Polymer.

### What's next?

We're currently researching a variety of things related to building Web Components and Progressive Web Apps, given that so much has changed in the web platform since we released our first production-quality version of the Polymer library. Stay tuned for blog posts and updates on our progress there, and check out [*Chrome Developer Summit*](https://developer.chrome.com/devsummit/) on October 23rd and 24th to hear about PWAs with Taylor Savage, and more on lit-html with Justin Fagnani-Bell. 


### Community and Ecosystem

The Polymer community has grown incredibly quickly and there are a number of individuals making extremely meaningful contributions to both the library and Polymer elements. We want to do more to highlight community work and generally better serve the Polymer and web components ecosystem. This means even more transparency around the core Polymer team's roadmap, more regular announcement and updates, and promoting element ownership beyond just the core Polymer team.

*Goals*:

- Accelerate Polymer + Community engagement.
  - Tighten the core Polymer team and community feedback loop - better evolve Polymer as the community evolves.
  - Publish all elements to npm and bower.
  - Regularly publish project and roadmap updates.
  - Work with community members to help drive elements forward.
  - Use [Polycasts](https://www.youtube.com/playlist?list=PLOU2XLYxmsII5c3Mgw6fNYCzaWrsM3sMN) to highlight awesome elements being built.


