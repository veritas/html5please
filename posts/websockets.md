feature: WebSockets
status: caution
tags: polyfill prefixes
kind: api
polyfillurls: [web-socket-js](https://github.com/gimite/web-socket-js)

Making your app real-time is a huge boost and [WebSockets](http://dev.w3.org/html5/websockets/) give you the ability to add bi-directional communication over a persistent connection to your application to increase interactivity and user engagement.

[web-socket-js](https://github.com/gimite/web-socket-js) is a natural polyfill for the JavaScript WebSocket API transferring data through Flash Sockets when WebSockets aren't available.

To use native WebSockets in Firefox, the prefixed MozWebSocket should be used. However, Firefox 11 will support the [IETF standard](http://tools.ietf.org/html/rfc6455) without the prefix.

The protocol backing the Web Socket API has become an IETF standard, but Safari has not yet implemented the new version. To support Safari, the WebSocket server needs to support both -76 and the RFC6455 versions, or you can use Flash or Java sockets (if available).

The -76 version has a possible security problem for users behind buggy transparent proxies. The same security problem exists with Flash sockets and Java sockets. None of these options are recommended.

To make websockets easier to use there are multiple server-side framework solutions. These frameworks generally provide fallback transports (HTTP long polling, HTTP streaming, ajax polling) to support non-websocket browsers. However be prepared to tune the fallback solutions in order to meet the needs of your app. 

[Sockjs](https://github.com/sockjs) is one a framework which emulates the WebSocket API in browsers and has server implementations for node.js, Ruby, Erlang or tornado. 

[Socket.io](http://socket.io/) is a Node.js framework that helps with downlevel transports for browsers lacking native WebSocket support (and supports IE6+).

XSockets is a .NET+JavaScript framework that handles fallback via Flash and Silverlight.

For more information see the [Full list of possible server-side websocket solutions](http://www.leggetter.co.uk/real-time-web-technologies-guide#self-hosted)
