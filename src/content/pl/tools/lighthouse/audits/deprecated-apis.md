project_path: /web/tools/_project.yaml book_path: /web/tools/_book.yaml description: Reference documentation for the "Avoids Deprecated APIs" Lighthouse audit.

{# wf_updated_on: 2018-07-23 #} {# wf_published_on: 2017-07-12 #} {# wf_blink_components: N/A #}

# Avoids Deprecated APIs {: .page-title }

## Overview {: #overview }

Deprecated APIs are scheduled to be removed from Chrome. Calling these APIs after they're removed will cause errors on your site.

## Recommendations {: #recommendations }

Lighthouse flags the deprecated APIs in your report. Go to [Chrome Platform Status](https://www.chromestatus.com/features#deprecated){:.external} and expand the entries for the APIs that you're using to learn more about why the APIs are deprecated, as well as how to replace them.

## More information {: #more-info }

Lighthouse collects the deprecated API warnings that Chrome logs to the DevTools Console.

[Audit source](https://github.com/GoogleChrome/lighthouse/blob/master/lighthouse-core/audits/deprecations.js){:.external}

## Feedback {: #feedback }

{% include "web/_shared/helpful.html" %}