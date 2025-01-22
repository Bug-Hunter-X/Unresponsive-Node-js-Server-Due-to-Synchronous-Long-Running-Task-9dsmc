# Unresponsive Node.js Server Due to Synchronous Long-Running Task

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in a request handler can make the server unresponsive.  The provided `bug.js` file showcases this problem. The solution, `bugSolution.js`, demonstrates how to fix this using asynchronous operations.

## Problem

The `bug.js` file contains a simple HTTP server. However, the request handler includes a `while` loop that simulates a long-running task, blocking the event loop and preventing the server from handling other requests. This results in the server becoming unresponsive.

## Solution

The `bugSolution.js` file demonstrates the correct approach.  Instead of blocking the event loop with a synchronous operation, it uses asynchronous techniques to handle the long-running task. This allows the event loop to continue processing other requests while the task runs in the background.