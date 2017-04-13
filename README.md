# HTML-Performance

## Link Type
[MDN Link types](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types)

## DNS prefetching
`<link rel="dns-prefetch" href="//example.com">`

browsers to start prefetching the DNS for that domain a fraction before it's actually needed.

## Preconnect
`<link rel="preconnect" href="http://css-tricks.com">`

the browser can set up the necessary sockets ahead of time and eliminate the costly DNS, TCP, and TLS roundtrips from the critical path of the actual request. 

## Prefetching
`<link rel="prefetch" href="image.png">`

Unlike DNS prefetching, we're actually requesting and downloading that asset and storing it in the cache. 

## Prerendering pages
`<link rel="prerender" href="http://css-tricks.com">`

This is like opening the URL in a hidden tab – all the resources are downloaded, the DOM is created, the page is laid out, the CSS is applied, the JavaScript is executed, etc.

## Preloading
`<link rel="preload" href="image.png">`

[W3 Preload](https://www.w3.org/TR/preload/)

it's best to always download an asset, regardless of whether the browser thinks that's a good idea or not
