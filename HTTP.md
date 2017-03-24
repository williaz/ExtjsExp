## OSI model
1. Physical layer: router...
2. Data link layer: wifi
3. Network layer: IP
4. Transport layer: TCP, TLS/SSL
5. ~~Session layer~~
6. ~~Presentation layer~~
7. Application layer: HTTP, FTP, DNS, SSH

## [Overview](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)
Hypertext Transfer Protocol (HTTP) is an application-layer protocol for transmitting hypermedia documents, such as HTML. 
- [ ] C/S
- [ ] Stateless

- It is an application layer protocol that is sent over TCP, or over a TLS-encrypted TCP connection

- New functionality can even be introduced by a simple agreement between a client and a server about a new header's semantics.

- While the core of HTTP itself is stateless, HTTP cookies allow the use of stateful sessions. Using header extensibility, HTTP Cookies are added to the workflow, allowing session creation on each HTTP request to share the same context, or the same state.

- Cache
 How documents are cached can be controlled by HTTP. The server can instruct proxies, and clients, what to cache and for how long. The client can instruct intermediate cache proxies to ignore the stored document.
- Sessions
 Using HTTP cookies allows you to link requests with the state of the server. This creates sessions, despite basic HTTP being a state-less protocol. 
 
## [Caches](https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching)
 
  When a web cache has a requested resource in its store, it intercepts the request and returns its copy instead of re-downloading from the originating server.

- Cache-Control:
- [ ] no-cache
- [ ] no-store
- [ ] private/public
- [ ] max-age=\<seconds>: Freshness lifetime
- [ ] must-revalidate

 - Cache eviction items are periodically removed from storage.
 
 Note that a stale resource is not evicted or ignored; when the cache receives a request for a stale resource, it forwards this requests with a If-None-Match to check if it isn't in fact still fresh. If so, the server returns a 304 (Not Modified) header without sending the body of the requested resource, saving some bandwidth.
 
- Validation(server return 200 or 304)

- [ ] ETag: The ETag response header is an opaque-to-the-useragent value that can be used as a strong validator. 
  If the ETag header was part of the response for a resource, the client can issue an If-None-Match in the header of future requests – in order to validate the cached resource.

- [ ] The Last-Modified response header can be used as a weak validator. It is considered weak because it only has 1-second resolution. If the Last-Modified header is present in a response, then the client can issue an If-Modified-Since request header to validate the cached document.

- When using the Vary: User-Agent header, caching servers should consider the user agent when deciding whether to serve the page from cache. 

  
 
 
 
 
 
 
 
 
 
