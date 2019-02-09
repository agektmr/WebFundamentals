project_path: /web/tools/_project.yaml book_path: /web/tools/_book.yaml description: Reference documentation for the "Elements With ARIA Roles Have The Required aria-* Attributes" Lighthouse audit.

{# wf_updated_on: 2018-07-23 #} {# wf_published_on: 2017-01-17 #} {# wf_blink_components: N/A #}

# Elements With ARIA Roles Have The Required aria-* Attributes {: .page-title }

## Overview {: #overview }

The `role` attribute helps screen readers understand the purpose of an ARIA widget. A `role` may have a set of required, additional attributes that describe the state of the widget to the screen reader.

See [Introduction to ARIA](/web/fundamentals/accessibility/semantics-aria/) for more information.

## Recommendations {: #recommendations }

<<_shared/query.md>>

To find each element's missing required attributes:

1. Note the `role` and `aria-*` attributes of the element.

2. Go to [Definition of Roles](https://www.w3.org/TR/wai-aria/roles#role_definitions).

3. Go to the page for this element's `role`.

4. Check the `aria-*` attributes of the element against the **Required States and Properties** list.

5. Add any attributes that are missing.

## More information {: #more-info }

This audit is powered by the aXe Accessibility Engine. See [Required ARIA attributes must be provided](https://dequeuniversity.com/rules/axe/1.1/aria-required-attr) for more information.

## Feedback {: #feedback }

{% include "web/_shared/helpful.html" %}