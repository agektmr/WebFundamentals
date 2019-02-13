project_path: /web/tools/_project.yaml book_path: /web/tools/_book.yaml description: Reference documentation for the "Time to Interactive" Lighthouse audit.

{# wf_updated_on: 2018-10-01 #} {# wf_published_on: 2018-08-16 #} {# wf_blink_components: Platform>DevTools #}

# Time to Interactive {: .page-title }

## Overview {: #overview }

<blockquote>
  <p>
    Load is not a single moment in time — it’s an experience that no one metric can fully capture.
    There are multiple moments during the load experience that can affect whether a user perceives
    it as "fast" or "slow".
  </p>
  <p>--- <a class="external" href="https://w3c.github.io/paint-timing/">Paint Timing spec</a></p>
</blockquote>

The Time to Interactive (TTI) metric measures how long it takes a page to become interactive. "Interactive" is defined as the point where:

* The page has displayed useful content, which is measured with [First Contentful Paint](/web/tools/lighthouse/audits/first-contentful-paint).
* Event handlers are registered for most visible page elements.
* The page responds to user interactions within 50 milliseconds.

Some sites optimize content visibility at the expense of interactivity. This can create a frustrating user experience. The site appears to be ready, but when the user tries to interact with it, nothing happens.

## Recommendations {: #recommendations }

To improve your TTI score, defer or remove unnecessary JavaScript work that occurs during page load. See [Optimize JavaScript Bootup](/web/fundamentals/performance/optimizing-content-efficiency/javascript-startup-optimization/) and [Reduce JavaScript Payloads with Tree Shaking](/web/fundamentals/performance/optimizing-javascript/tree-shaking/), and [Reduce JavaScript Payloads with Code Splitting](/web/fundamentals/performance/optimizing-javascript/code-splitting/).

### Tracking TTI in the real world {: #RUM }

To measure when TTI actually occurs on your users' devices, see [Tracking TTI](/web/fundamentals/performance/user-centric-performance-metrics#tracking_tti). The code snippet describes how to programmatically access TTI data and submit it to Google Analytics.

TTI can be difficult to track in the wild. You may prefer to track [First Input Delay](/web/updates/2018/05/first-input-delay), instead.

## More information {: #more-info }

See [Definition](https://github.com/WICG/time-to-interactive#definition){: .external } for more details on how exactly TTI is calculated.

This metric was previously called Consistently Interactive.

Sources:

* [Audit source](https://github.com/GoogleChrome/lighthouse/blob/master/lighthouse-core/audits/metrics/interactive.js){:.external}
* [Time to Interactive Explainer](https://github.com/WICG/time-to-interactive){: .external }
* [First Interactive and Consistently Interactive](https://docs.google.com/document/d/1GGiI9-7KeY3TPqS3YT271upUVimo-XiL5mwWorDUD4c){: .external }

## Feedback {: #feedback }

{% include "web/_shared/helpful.html" %}