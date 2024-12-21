# Node.js Server Hanging Bug

This repository demonstrates a common issue in Node.js: blocking the event loop.  The server hangs for 5 seconds due to a long-running synchronous operation, preventing it from handling other requests.  This can lead to unresponsive servers and poor performance.

## Bug

The `server.js` file contains a simple HTTP server that simulates a long-running task using a `while` loop. This blocks the event loop, preventing the server from responding to new requests during that 5-second period.

## Solution

The `serverSolution.js` file demonstrates a solution using asynchronous operations and promises to avoid blocking the event loop.  Asynchronous operations allow the server to continue handling other requests while the long-running task executes in the background. 

## How to reproduce:

1. Clone this repository.
2. Navigate to the directory containing `server.js` and `serverSolution.js`.
3. Run `node server.js` in your terminal. 
4. Observe the server hangs during the 5 seconds, unable to handle new requests.
5. Run `node serverSolution.js` to see a corrected version.
