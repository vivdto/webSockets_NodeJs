Real-Time! No latency! Speed! Optimization! is some vocabulary that every developer or product should have in their whitelist; isn’t it?

…Polling?
Who likes Polling (Short polling and long polling are both asynchronous communication techniques in JavaScript. Asynchronous communication allows data to be retrieved from servers without blocking the user interface.) for a message to come, or what if it does not come? … like your past! :P And you’re wasting your resources! :(


HTTP, being dependent on client requests!
In the day and age of live streaming, video conferencing, and remote work, one of the primary concerns of any user is latency (delay). A seamless experience is the name of the game ;)

Traditional HTTP, being dependent on client requests, is simply not capable of fulfilling this need. They’re simply too slow. It needs to be upgraded, literally.


So we have something in-house; WebSockets… An event-driven, web-friendly alternative to HTTP.

WebSockets are an upgrade to traditional HTTP.
Websockets don’t require a client request to fetch data from the server every time, fulfilling the need for real-time updates.

Wondering how? Let’s find it out! In simple terms, WebSockets are an upgrade to traditional HTTP.


Whenever a websocket request is made to regular HTTP, it is actually upgraded to a WebSocket connection.

…your underlying TCP connection will remain the same!
However, this happens only at the protocol level, meaning that your underlying TCP connection will remain the same as it was when working on the HTTP protocol.

To use a WebSocket, a client first sends a request to upgrade the server.
If the server supports websockets, which these days it usually does, it will accept the request and switch the protocols from HTTP to WebSocket.
WebSocket connection (event-driven), the server simply pushes every new message (the event) it receives directly to the client.

Once the protocol switching is successful, the HTTP server becomes a WebSocket server and a persistent connection is created between the client and the server.
Next, the WebSocket server waits for an event to happen and once it does it performs the function attached to the event.

For example, in a chat application, you don’t have to place a request for the next message every time.

…unlike HTTP, which is stateless
Being a WebSocket connection (event-driven), the server simply pushes every new message (the event) it receives directly to the client.

WebSockets maintain their state (unlike HTTP, which is stateless) and utilize a full-duplex connection.

WebSockets have speeds 5–7 times better than traditional HTTP.
Websockets are mostly used in places where real-time updates are necessary.


WebSockets always maintain their state (unlike HTTP, which is stateless) and utilize a full-duplex connection.

Furthermore, headers in WebSockets are sent only once while sending the upgrade request. This is why WebSockets have speeds 5–7 times better than traditional HTTP.

Implementing the server
Now let’s code the server-side javascript. Add the following code to index.js the server folder.

import express from "express";

import { WebSocketServer } from "ws";

const app = express();
const port = 8080;

const server = app.listen(port, () =>{
    
console.log("Server is listening...");


});

const wss = new WebSocketServer({server});

wss.on("connection", (ws) =>{
    ws.on("message", (data)=>{
        console.log("data from client : %s", data);

        ws.send("Thanks buddy! We are responding in real-time ;) ");


    });

});
Resource: VSCode, NodeJs, Express, WS, HoppScotch.io, Dev.to.

Stay Awake
Vivashwat!

:)
