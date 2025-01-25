# Node.js Server Unresponsiveness

This repository demonstrates a common Node.js issue where a long-running operation in the request handler blocks the event loop, causing the server to become unresponsive.  The solution showcases how to use asynchronous operations (using promises or async/await) to prevent blocking.

## Bug

The `server.js` file contains a simple HTTP server with a request handler that simulates a long-running operation. This operation blocks the event loop for 5 seconds, preventing the server from processing any new requests during that time.  This will lead to dropped connections and an unresponsive application.

## Solution

The `server-fixed.js` demonstrates how to resolve this issue using asynchronous operations.  By performing the task asynchronously, the event loop remains free to process other requests while the long-running operation completes in the background.