# Client HTML-Performance

## Link Type
- [MDN Link types](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types)
- [key CDN](https://www.keycdn.com/blog/resource-hints/)

## DNS Prefetching
`<link rel="dns-prefetch" href="//example.com">`

browsers to start prefetching the DNS for that domain a fraction before it's actually needed.

## Preconnect
`<link rel="preconnect" href="http://css-tricks.com">`

the browser can set up the necessary sockets ahead of time and eliminate the costly DNS, TCP, and TLS roundtrips from the critical path of the actual request. 

## Prefetching
- [Key CDN](https://www.keycdn.com/support/prefetching/)
- [MSDN Support](https://msdn.microsoft.com/en-us/library/dn265039(v=vs.85).aspx)
`<link rel="prefetch" href="image.png">`

Unlike DNS prefetching, we're actually requesting and downloading that asset and *storing it in the cache*. This is a low priority fetch and the main use case is to speed up the next navigation rather than the current one.

Use when:
- require resources in cache
- fetch resources on other pages


## Prerendering pages
`<link rel="prerender" href="http://css-tricks.com">`

This is like opening the URL in a hidden tab – all the resources are downloaded, the DOM is created, the page is laid out, the CSS is applied, the JavaScript is executed, etc.

*Not supported by most browser*
*Can't use Chrome devtool to check* 

[Chrome Prerender Utility](chrome://net-internals/#prerender)

## Preloading
`<link rel="preload" href="image.png">`

- [W3 Preload](https://www.w3.org/TR/preload/)
- [Smashing Magazing](https://www.smashingmagazine.com/2016/02/preload-what-is-it-good-for/)

It's best to always download an asset, regardless of whether the browser thinks that's a good idea or not.  It is aim to speed up the *current navigation* and fetch resources with high-priority

Use when:
- get resouces for currect page

# Server Performance
## Cache-Control
[Cache-control](https://varvy.com/pagespeed/cache-control.html)
