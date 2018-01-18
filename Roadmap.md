# Roadmap

An overview of what the core Polymer team is looking to work on over the next few months.

As a caveat - this is a living doc, and will evolve as priorities grow and shift. The Polymer project will always be adapting to new use-cases and evolutions in the platform - this roadmap is more of a "North Star" of what we're looking to work on than a strict timeline.

Please feel free to file issues on this repository if you have questions, concerns, or suggestions.

Last Updated: 1/18/2018 by arthurevans

### Polymer 3.0 (preview)

We announced an early sneak preview of Polymer 3.0 at [Polymer Summit 2017](https://www.youtube.com/watch?v=TDpiyrcOO30&list=PLNYkxOF6rcIDP0PqVaJxqNWwIgvoEPzJi). We then posted a two-part series on [what Polymer 3.0 entails](https://www.polymer-project.org/blog/2017-08-22-npm-modules.html) and [how to get started](https://www.polymer-project.org/blog/2017-08-23-hands-on-30-preview.html) with it. 

In summary: We're migrating to npm from Bower; migrating to ES Modules from HTML Imports; and not planning to change the API from Polymer 2.0. Because of that, the changes will be minimal and mechanical, so we built the Polymer Modulizer to automate the upgrade.  

We're planning to release Polymer 3.0 by the end of Q1, 2018. Until the release, we're planning on bi-weekly updates
to the preview code on npm under the `@next` tag.

Most 3.0-related work is taking place in the [Polymer Modulizer](https://github.com/Polymer/polymer-modulizer) repo. 

Most elements are now being automatically converted for 3.0, but in many cases tests aren't running at all or some tests are broken. For details, see the [Polymer 3.0 element status page](https://github.com/Polymer/polymer-modulizer/blob/master/docs/polymer-3-element-status.md).

The following items are on the roadmap for Polymer 3.0:

-   Better support for incremental conversion in Modulizer. Instead of requiring you to convert an entire set of packages 
    in one batch, Modulizer will output a manifest of the conversion for each package. The manifest can be published to npm 
    along with the converted package. When converting, Modulizer will read the published manifests of dependencies
    and skip conversion for dependencies that have already been converted and published.
-   JavaScript Module bundling. Polymer Bundler will produce either HTML imports based bundles or JS modules based bundles.
-   Bare-specifier support: Analyzer will resolve them, `polymer-build` and `polyserve` will rewrite them.
-   Support for dynamic `import()`: `polymer-build` and `polyserve` can rewrite these when compiling out modules.
-   Support for `import.meta.url`: Polymer Bundler, `polymer-build` and `polyserve` will rewrite these references for 
    browsers that don't support this property.
-   Updated documentation for Polymer 3.0.
-   Updated versions on Polymer Starter Kit and other templates for Polymer 3.0.


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


