project_path: /web/tools/_project.yaml book_path: /web/tools/_book.yaml description: Reference documentation for the "Offscreen Images" Lighthouse audit.

{# wf_updated_on: 2018-12-17 #} {# wf_published_on: 2017-05-31 #} {# wf_blink_components: N/A #}

# Offscreen Images {: .page-title }

## Overview {: #overview }

Offscreen images are images that appear [below the fold](https://en.wikipedia.org/wiki/Above_the_fold#Below_the_fold). Since users can't see offscreen images when they load a page, there's no reason to download the offscreen images as part of the initial page load. In other words, deferring the load of offscreen images can speed up page load time and time to interactive.

## Recommendations {: #recommendations }

To pass this audit, refactor your pages to only download above-the-fold images during the initial request. Applying this strategy to your JS, HTML, CSS, and other resources can also speed up page load time. See [Critical Rendering Path](/web/fundamentals/performance/critical-rendering-path/) to learn more.

Consider using an [IntersectionObserver](/web/updates/2016/04/intersectionobserver) to intelligently determine when to lazy-load offscreen images. For example, suppose you have some images at the bottom of a very long page. With an IntersectionObserver, you can load the images only when the user has scrolled halfway down the page. See [Intersect all the things!](/web/updates/2016/04/intersectionobserver#intersect_all_the_things) for more on this approach.

If you do use an IntersectionObserver, make sure to include the [polyfill](https://github.com/w3c/IntersectionObserver/tree/master/polyfill), because native browser support is limited.

## More information {: #more-info }

Lighthouse flags offscreen images that were requested before the Time To Interactive (TTI) event.

## Feedback {: #feedback }

{% include "web/_shared/helpful.html" %}