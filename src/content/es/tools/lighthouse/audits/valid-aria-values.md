project_path: /web/tools/_project.yaml book_path: /web/tools/_book.yaml description: Reference documentation for the "Element aria-* Attributes Have Valid Values" Lighthouse audit.

{# wf_updated_on: 2018-07-23 #} {# wf_published_on: 2017-01-18 #} {# wf_blink_components: N/A #}

# Element aria-* Attributes Have Valid Values {: .page-title }

## Overview {: #overview }

Invalid ARIA attribute values may be preventing the screen reader from properly understanding the current state of a widget. This could make the page unusable to users who rely on screen readers.

See [Introduction to ARIA](/web/fundamentals/accessibility/semantics-aria/) for more information.

## Recommendations {: #recommendations }

<<_shared/query.md>>

To find each listed element's invalid attribute values:

1. Note the `aria-*` attributes of the element.

2. Go to [Definition of States and Properties](https://www.w3.org/TR/wai-aria/states_and_properties#state_prop_def).

3. For each `aria-*` attribute of the element, go the page for that attribute.

4. Make the value of the element's attribute match one of the supported values listed in **Value**.

## More information {: #more-info }

This audit is powered by the aXe Accessibility Engine. See [ARIA attributes must conform to valid values](https://dequeuniversity.com/rules/axe/1.1/aria-valid-attr-value) for more information.

## Feedback {: #feedback }

{% include "web/_shared/helpful.html" %}