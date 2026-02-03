
# General topics

## Websocket and Socket.io
* What is WebSocket, how does it differ from HTTP?

    : WebSocket is an application-layer protocoll like HTTP, and it is used for bidirectional communication over the a single TCP connection. This means that WebSocket uses a persistent connection while HTTP works with a stateless request-response model. WebSocket is used when two way communication is necessary because in these use cases the WebSocket protocoll is much faster than the HTTP solutions for them (like polling or long polling).

* What is some common use case for WebSocket?

    : WebSocket is useful when we need real-time communication between the server and the clients (or between the clients through the server). Multiplayer games, two-way communication platforms like Zoom or Teams, collaborative document editing like Google Docs or any app where the server needs to notify or update information to the client are all good examples for use cases of WebSocket.

* How does the WebSocket handshake work?

    : To establish WebSocket connection, the client has to send an HTTP request to the server. If the server is ready for the WebSocket connection it responses with a 101 (switching protocols) response. After that client and server can use the WebSocket protocol to send messages to each other.

* What is a WebSocket frame?

    : Websocket frame is the structure the client and the server uses to communicate with each other after the initiating handshake. It's the smallest unit of data sent over the WebSocket connection. A frame consists a header and the application data. A frame has an attribute of `fin` (it can be a `fin` frame or not) which flag if a frame is a closing one, which is important for fragmented message (the ones be formed by more than one frame).

* What WebSocket frame types are there?

    : In WebSocket protocol there are control and non-control frames. A non-control frame can be `text`, `binary` or `continue` type. The first two can be the first frame's type of a fragmented message or the sole frame's type of an unfragmented one and the main difference between them is that the `text` frame has to be valid UTF-8. A `continue` frame is the type of the following frame or frames in a fragmented message, and the final frame's `fin` attribute is set to 1 to flag the end of the message. At one time only one message can be handled by the protocol, there are no parallel messages in WebSocket.
    A control frame can be `ping`, `pong` and `close` type and they must not be part of fragmented messages, but they can be sent between two non-control frames those belong to the same fragmented message. If a party receive a `ping` frame it has to send back a `pong` frame immediately with the same payload. They are particularly useful to check if a connection is still alive or not. If a party receives a `close` frame it has to respond with another one and close the underlying TCP connection. Any frame that is received after a `close` frame must be discarded.

* What is the difference between WebSocket and SSE (Server Sent Events)?

    : An SSE is a server-push technology which enable the server to push updates to a client via HTTP connection. It's unidirectional (only the server can send messages to the client), persistent connection and if the connection drops the client (browser) automatically tries to reconnect. And the WebSocket is a bidirectional protocol for two-way communication between server and client and uses HTTP only for the initial handshake.

* What fallback mechanisms can be used instead of WebSocket?

    : The most simple alternative to WebSocket is polling, which means the client sends HTTP requests in regular intervals to check if there is new information the server should send to it; if there is then the server can include it in the response. It requires a lot of HTTP connection to establish. Long polling also uses HTTP protocol, but in this case the server holds back the response until there isn't new information it wants to send to the client. Upon receiving a response the client send another request. Another alternative is using HTTP for client-initiated communication and SSE for server-initiated data sharing at the same time, this is what ChatGPT uses to stream text and receive prompt from the client at the same time.

* What is Socket.io?
* What are the key features of Socket.io?
* What is a socket id in Socket.io?
* How do you send a message to a specific client in Socket.io?
* How do you define an event handler in Socket.io?
* What are rooms in Socket.io, and how do you use them?
* What is `socket.broadcast.emit()` and when should it be used?

