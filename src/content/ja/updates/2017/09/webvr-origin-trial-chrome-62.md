project_path: /web/_project.yaml book_path: /web/updates/_book.yaml description: Learn about what is changing in the WebVR API.

{# wf_updated_on: 2017-09-28 #} {# wf_published_on: 2017-09-28 #} {# wf_tags: news,webvr #} {# wf_featured_snippet: Learn about what is changing in the WebVR API #} {# wf_blink_components: Blink>WebVR #}

# WebVR changes in Chrome 62 {: .page-title }

{% include "web/_shared/contributors/mscales.html" %}

The current WebVR origin trial is ending on November 14, 2017, shortly after the stable release of Chrome 62. We have begun a new trial with the WebVR 1.1 API in Chrome 62 that will continue through Chrome 64.

The new trial includes some API behavior updates that are consistent with the direction of the forthcoming [WebVR 2.0 spec](https://github.com/w3c/webvr/blob/master/explainer.md):

- Use of WebVR is restricted in cross-origin iframes. If you intend for embedded cross-origin iframes to be able to use WebVR, add the attribute `allow="vr"` to the iframe tag, or use a [Feature-Policy](https://docs.google.com/document/d/1k0Ua-ZWlM_PsFCFdLMa8kaVTo32PeNZ4G7FFHqpFx4E/edit#heading=h.4yubgixv5l6b) header ([spec discussion](https://github.com/w3c/webvr/issues/86), [bug](https://bugs.chromium.org/p/chromium/issues/detail?id=666767)).
- Limit use of `getFrameData()` and `submitFrame()` to `VRDisplay.requestAnimationFrame()` ([spec discussion](https://github.com/w3c/webvr/issues/246), [bug](https://bugs.chromium.org/p/chromium/issues/detail?id=736023)).
- `window.requestAnimationFrame()` does not fire if the page is not visible, meaning it will not fire on Android while WebVR is presenting ([spec discussion](https://github.com/w3c/webvr/issues/225), [bug](https://bugs.chromium.org/p/chromium/issues/detail?id=718246)).
- The synthetic click event at viewport (0, 0) has been removed (for both Cardboard and the Daydream controller touchpad) ([bug](https://bugs.chromium.org/p/chromium/issues/detail?id=716571)). The `vrdisplayactivate` event is now considered a user gesture, and may be used to request presentation and begin media playback, without relying on the click event. Code that was previously relying on click event handlers for input should be converted to check for gamepad button presses. ([Example implementation](https://github.com/toji/webvr.info/commit/d73e6182287e3c6c0daa4d3d2ea578a31a2e5a6b))
- Chrome may exit presentation if the page takes greater than 5 seconds to display the first frame ([code change](https://chromium-review.googlesource.com/c/chromium/src/+/636386)). It is recommended that the page display within two seconds and that a splash screen is used if needed.

Your current WebVR Origin Trial tokens will not be recognized by Chrome 62. To participate in this new trial please [use the sign up form](https://bit.ly/OriginTrialSignup).