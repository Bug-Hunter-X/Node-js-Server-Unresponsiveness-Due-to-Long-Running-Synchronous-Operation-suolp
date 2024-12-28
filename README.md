# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in a request handler blocks the event loop, causing the server to become unresponsive to new requests.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a corrected version.

## Problem

The server uses a `while` loop to simulate a time-consuming task within the request handler. This blocks the event loop, preventing the server from handling subsequent requests until the loop completes.  This can lead to poor performance and server unresponsiveness.

## Solution

The solution involves using asynchronous operations to prevent blocking the event loop.  The improved code utilizes techniques like `setTimeout` or promises to handle long-running operations without blocking the main thread.