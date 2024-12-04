# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js applications: server unresponsiveness caused by a blocking operation within the request handler.  The provided `server.js` file contains a simple HTTP server that simulates a long-running task (5-second delay).  During this delay, the server is unable to accept or process new requests, leading to a hang.

The `serverSolution.js` file offers a solution using asynchronous operations to prevent blocking and maintain server responsiveness.

## Problem

Node.js is single-threaded.  Long-running operations in the main event loop block the processing of other requests. This leads to unresponsiveness and poor performance.

## Solution

The solution employs asynchronous programming (e.g., using callbacks, promises, or async/await) to prevent the main thread from being blocked.  Offload long-running tasks to separate threads or worker processes to maintain server responsiveness.