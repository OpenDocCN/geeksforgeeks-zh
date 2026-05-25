# Node.js HTTP2 Server Response 'finish' Event

> 原文: [https://www.geeksforgeeks.org/node-js-http2serverresponse-finish-event/](https://www.geeksforgeeks.org/node-js-http2serverresponse-finish-event/)

The `'finish'` event in an HTTP2 server is emitted when the response headers and the last chunk of the body have been sent.

## Syntax

```js
Event: 'finish'
```

## Parameters

This event does not accept any parameters.

## Return Value

This event returns only a callback function.

## How to Generate Private and Public Key Certificates?

### 1. Filename: private-key

Open Notepad, copy and paste the following key, and save the file as `private-key.pem`.

### 2. Filename: public-cert

Open Notepad, copy and paste the following key, and save the file as `public-cert.pem`.

## Example 1

**Filename: index.js**

```js
// Node.js program to demonstrate the
// Http2ServerResponse 'finish' event

const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

  // Emitting finish event
  response.on('finish', () => {
    console.log("response has been sent")
  })
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(
  options, http2Handlers);

server.on('stream', (stream, requestheader) => {
  stream.respond({
    ':status': 200,
    'content-type': 'text/plain'
  });
  stream.write('hello ');

  // Getting all information of this http2stream
  // object by using state method
  const status = stream.state;

  stream.end("priority weight : " + status.weight);

  // Stopping the server
  // by using the close() method
  server.close(() => {
    console.log("server destroyed");
  })
});

server.listen(8000);

// Creating and initializing client
// by using tls.connect() method
const client = http2.connect('http://localhost:8000');

const req = client.request({ ':method': 'GET',
  ':path': '/name'});

req.on('response', (responsesocket) => {
  console.log("status : " + responsesocket[":status"]);
});

req.on('data', (data) => {
  console.log('Received: %s ',
    data.toString().replace(/(\n)/gm, ""));
});

req.on('end', () => {
  client.close(() => {
    console.log("client destroyed");
  })
});
```

Run the `index.js` file using the following command:

```bash
node index.js
```

**Output:**

```js
response has been sent
status : 200
Received: hello
Received: priority weight : 16
client destroyed
server destroyed
```

## Example 2

**Filename: index.js**

```js
// Node.js program to demonstrate the
// Http2ServerResponse 'finish' event

const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

  // Emitting finish event
  response.on('finish', () => {
    console.log("response has been sent")
  })
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options, http2Handlers);

server.on('stream', (stream, requestHeaders) => {

  // Getting all information of this http2stream object
  // by using state method
  const status = stream.state;

  stream.end("The sum weight of all Http2Stream : " +
    status.sumDependencyWeight);

  stream.close()

  // Stopping the server
  // by using the close() method
  server.close(() => {
    console.log("server destroyed");
  })
});

server.listen(8000);

// Creating and initializing client
// by using tls.connect() method
const client = http2.connect('http://localhost:8000');

const req = client.request({ ':method': 'GET',
  ':path': '/www.geeksforgeeks.org' });

req.on('data', (data) => {
  console.log('Received: %s ',
    data.toString().replace(/(\n)/gm, ""));
});

req.on('end', () => {
  client.close(() => {
    console.log("client destroyed");
  })
});
```

Run the `index.js` file using the following command:

```bash
node index.js
```

**Output:**

```js
response has been sent
Received: The sum weight of all Http2Stream : 0
client destroyed
server destroyed
```

**Reference:** [https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_event_finish](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_event_finish)