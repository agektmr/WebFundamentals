project_path: /web/tools/_project.yaml book_path: /web/tools/_book.yaml description: Reference documentation for the "Avoids Enormous Network Payloads" Lighthouse audit.

{# wf_updated_on: 2018-07-23 #} {# wf_published_on: 2017-06-21 #} {# wf_blink_components: N/A #}

# Avoids Enormous Network Payloads {: .page-title }

## Overview {: #overview }

Reducing the total size of network requests speeds up page load time and saves your users money that they would have spent on cellular data.

See [Highest Correlation To Load Time](http://httparchive.org/interesting.php#onLoad) to view the correlation between requests and load time.

See [What Does My Site Cost](https://whatdoesmysitecost.com/) to calculate the cost of viewing your site around the world. You can adjust the results to factor in purchasing power.

## Recommendations {: #recommendations }

Click **View Details** to see your page's requests. The largest requests are presented first. Reduce the size of the requests to reduce your total payload size.

Here are some strategies for reducing payload size:

* Defer requests until they're needed. See [The PRPL Pattern](/web/fundamentals/performance/prpl-pattern/) for one possible approach.
* Optimize requests to be as small as possible. Possible techniques include: 
    * [Enable text compression](/web/tools/lighthouse/audits/text-compression#recommendations).
    * Minify HTML, JS, and CSS. See [Minification](/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer#minification_preprocessing_context-specific_optimizations).
    * Use WebP instead of JPEG or PNG. See [Serve Images As WebP](/web/tools/lighthouse/audits/webp).
    * Set the compression level of JPEG images to 85. See [Optimize Images](/web/tools/lighthouse/audits/optimize-images#recommendations).
* Cache requests so that the page doesn't re-download the resources on repeat visits. See [HTTP Caching](/web/fundamentals/performance/optimizing-content-efficiency/http-caching) and [Service Workers: An Introduction](/web/fundamentals/getting-started/primers/service-workers).

## More information {: #more-info }

Lighthouse sums up the total byte size of all resources that the page requested.

The target score of 1600KB is based on what a page can theoretically download on a 3G connection, while still achieving a time-to-interactive of 10 seconds or less. See [googlechrome/lighthouse/pull/1759](https://github.com/GoogleChrome/lighthouse/pull/1759) for the original discussion.

The 0 to 100 score is calculated from a lognormal distribution.

[Audit source](https://github.com/GoogleChrome/lighthouse/blob/master/lighthouse-core/audits/byte-efficiency/total-byte-weight.js){:.external}

## Feedback {: #feedback }

{% include "web/_shared/helpful.html" %}