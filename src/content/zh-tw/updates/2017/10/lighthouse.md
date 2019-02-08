project_path: /web/_project.yaml book_path: /web/updates/_book.yaml description: Five new audits, the chrome-launcher standalone Node module, and a new throttling guide.

{# wf_updated_on: 2017-10-17 #} {# wf_published_on: 2017-10-17 #} {# wf_tags: lighthouse #} {# wf_featured_image: /web/progressive-web-apps/images/pwa-lighthouse.png #} {# wf_featured_snippet: Five new audits, the chrome-launcher standalone Node module, and a new throttling guide. #}

# Lighthouse 2.5 Updates {: .page-title }

{% include "web/_shared/contributors/vinamratasingal.html" %} {% include "web/_shared/contributors/brendankenny.html" %}

[Lighthouse](/web/tools/lighthouse/) 2.5 is now released! Highlights include:

* [chrome-launcher available as a standalone Node module](#launcher).
* [Five new audits](#audits).
* [A new throttling guide for advanced audiences](#throttling).

See the [release notes](https://github.com/GoogleChrome/lighthouse/releases/tag/v2.5.0#chrome-launcher) for the full list of new features, changes, and bug fixes coming to Lighthouse in version 2.5.

## chrome-launcher is now a standalone Node module {: #launcher }

[chrome-launcher](https://www.npmjs.com/package/chrome-launcher) is now a standalone Node module, making it easier to launch Google Chrome from your own Node applications.

## Five new audits {: #audits }

### Appropriate aspect ratios {: #aspect }

*Category: Best Practices*

The **Does not use images with appropriate aspect ratios** audit alerts you when an image's rendered aspect ratio is significantly different than the image's actual dimensions. The aspect ratio is the ratio between width and height. If the ratio is significantly different when rendered, then the image probably looks distorted.

<figure>
  <img src="/web/updates/images/2017/10/aspect.png"
       alt="The \&quot;Does not use images with appropriate aspect ratios\&quot; audit"
  <figcaption>
    <b>Figure 1</b>. The <b>Does not use images with appropriate aspect
    ratios</b> audit
  </figcaption>
</figure>

### JavaScript libraries with security vulnerabilities {: #security }

*Category: Best Practices*

The **Includes front-end JavaScript libraries with known security vulnerabilities** audit warns you about how many vulnerabilities a library has, as well as the highest severity level among those vulnerabilities.

<figure>
  <img src="/web/updates/images/2017/10/security.png"
       alt="The \&quot;Includes front-end JavaScript libraries with
            known security vulnerabilities\&quot; audit"
  <figcaption>
    <b>Figure 2</b>. The <b>Includes front-end JavaScript libraries
    with known security vulnerabilities</b> audit
  </figcaption>
</figure>

### Unused JavaScript {: #unused }

*Category: Performance*

The **Unused JavaScript** audit breaks down how much JavaScript a page loads but does not use during startup.

Note: This audit is only available when running Lighthouse from Node or the command line in [full-config mode](https://github.com/GoogleChrome/lighthouse/blob/master/lighthouse-core/config/full-config.js).

<figure>
  <img src="/web/updates/images/2017/10/unused.png"
       alt="The \&quot;Unused JavaScript\&quot; audit"
  <figcaption>
    <b>Figure 3</b>. The <b>Unused JavaScript</b> audit 
  </figcaption>
</figure>

### Low server response times {: #ttfb }

*Category: Performance*

The **Keep server response times low (TTFB)** audit measures how long it takes the client to receive the first byte of the main document. If Time To First Byte (TTFB) is long, then the request is taking a long time traveling through the network, or the server is slow.

<figure>
  <img src="/web/updates/images/2017/10/ttfb.png"
       alt="The \&quot;Keep server response times low\&quot; audit"
  <figcaption>
    <b>Figure 4</b>. The <b>Keep server response times low</b> audit
  </figcaption>
</figure>

### Console errors {: #errors }

*Category: Best Practices*

The **Browser errors were logged to the console** audit alerts you to any errors that are logged to the console as the page loads.

<figure>
  <img src="/web/updates/images/2017/10/errors.png"
       alt="The \&quot;Browser errors were logged to the console\&quot; audit"
  <figcaption>
    <b>Figure 5</b>. The <b>Browser errors were logged to the console</b>
    audit
  </figcaption>
</figure>

## Throttling guide {: #throttling }

Check out the new [Throttling Guide](https://github.com/GoogleChrome/lighthouse/blob/master/docs/throttling.md) to learn how to conduct high-quality, packet-level throttling. This guide is intended for advanced audiences.