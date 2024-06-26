# What is Node.js?

Node.js is <b>an open-source, cross-platform JavaScript runtime environment that executes JavaScript code outside a web browser.</b>

- Node.js is not a programming language like Python, Java or C/C++. Node.js is a runtime, similar to Java virtual machine, that converts JavaScript code into machine code.
- Node.js uses asynchronous programming!
- Node.js runs single-threaded, non-blocking, asynchronous programming, which is very memory efficient.
- common task for a web server can be to open a file on the server and return the content to the client.
 
<h3>Features Of Node.js:</h3>   

1. <b>Easy:</b> Node.js is quite easy to start with. It’s a go-to choice for web development beginners. With a lot of tutorials and a large community—getting started is very easy.
2. <b>Scalable:</b> It provides vast scalability for applications. Node.js, being single-threaded, is capable of handling a huge number of simultaneous connections with high throughput.
3. <b>Speed:</b> Non-blocking thread execution makes Node.js even faster and more efficient.
4. <b>Packages:</b> A vast set of open-source Node.js packages is available that can simplify your work. There are more than one million packages in the NPM ecosystem today.
5. <b>Strong:</b> Node.js is written in C and C++, which makes it speedy and adds features like networking support.
6. <b>Multi-platform:</b> Cross-platform support allows you to create SaaS websites, desktop apps, and even mobile apps, all using Node.js.
7. <b>Maintainable:</b> Node.js is an easy choice for developers since both the frontend and backend can be managed with JavaScript as a single language.

<h3>Drawbacks Of Node.js:</h3>

1. <b>CPU-bound Tasks:</b> Node.js is less suitable for CPU-intensive operations. Since the event loop is single-threaded, long-running calculations can block the event loop and delay processing of other requests.
2. <b>Callback Hell:</b> The heavy reliance on callbacks can lead to a phenomenon known as "callback hell" or "pyramid of doom," where the code becomes nested and difficult to read and maintain. However, this can be mitigated with Promises and async/await.
3. <b>Error Handling:</b> In a single-threaded environment, uncaught exceptions can crash the entire process. Therefore, robust error handling is crucial.
4. <b>Understanding Asynchrony:</b> Developers need to understand asynchronous programming and its quirks, which can have a learning curve.

In summary, Node.js is highly efficient for I/O-bound and scalable network applications, but less ideal for CPU-heavy operations. Its single-threaded, event-driven architecture allows it to handle multiple requests concurrently, providing an advantage in building efficient and scalable web applications. However, understanding its model and handling its asynchronous nature and error handling is crucial for developers.

# Applications of Node.js

<p align="center">
  <img src="https://github.com/omar-gamel/nodejs-article/blob/main/nodejs-applications.png" alt="Applications of Node.js" width="500" height="400">
</p>

Node.js is used for building different type of applications. Some of the application types are listed below −

1. <b>Streaming applications:</b> Node.js can easily handle real-time data streams, where it is required to download resources on-demand without overloading the server or the user’s local machine. Node.js can also provide quick data synchronization between the server and the client, which improves user experience by minimizing delays using the Node.js event loop.

2. <b>Single page apps:</b> Node.js is an excellent choice for SPAs because of its capability to efficiently handle asynchronous calls and heavy input/output(I/O) workloads. Data driven SPAs built with Express.js are fast, efficient and robust.

3. <b>Realtime applications:</b> Node.js is ideal for building lightweight real-time applications, like messaging apps interfaces, chatbots etc. Node.js has an event- based architecture, as a result has an excellent WebSocket support. It facilitates real-time two-way communication between the server and the client.

4. <b>APIs:</b> At the heart of Node.js is JavaScript. Hence, it becomes handling JSON data is easier. You can therefore build REST based APIs with Node.js
   
# Node.js Architecture and How It Works

Node.js uses the <b>Single Threaded Event Loop</b> architecture to handle multiple clients at the same time. To understand how this is different from other runtimes, we need to understand how multi-threaded concurrent clients are handled in languages like Java.

In a multi-threaded request-response model, multiple clients send a request, and the server processes each one before sending the response back. However, multiple threads are used to process concurrent calls. These threads are defined in a thread pool, and each time a request comes in, an individual thread is assigned to handle it.

<p align="center">
  <img src="https://github.com/omar-gamel/nodejs-article/blob/main/nodejs-architectures.png" alt="Node.js Architecture" width="500" height="300">
</p>

Node.js works differently. Let’s take a look at each step it goes through:

1. Node.js maintains a limited thread pool to serve requests.
2. Whenever a request comes, Node.js places it into a queue.
3. Now, the single-threaded <b>Event loop</b>—the core component—comes into the picture. This event loop waits for requests indefinitely.
4. When a request comes in, the loop picks it up from the queue and checks whether it requires a blocking input/output (I/O) operation. If not, it processes the request and sends a response.
5. If the request has a blocking operation to perform, the event loop assigns a thread from the internal thread pool to process the request. There are limited internal threads available. This group of auxiliary threads is called the worker group.
6. The event loop tracks blocking requests and places them in the queue once the blocking task is processed. This is how it maintains its non-blocking nature.
   
Since <b>Node.js uses fewer threads, it utilizes fewer resources/memory, resulting in faster task execution</b>. So for our purposes, this single-threaded architecture is equivalent to multi-threaded architecture. When one needs to process data-intensive tasks, then using multi-threaded languages like Java makes much more sense. But for real-time applications, Node.js is the obvious choice.

# Problems are created by Node.js being single threaded

Node is not completely single threaded. It uses thread pool for accessing resources, etc.

However, your code will run in single thread only and so you can’t do anything complicated. If your code needs to process data for each request and it’s going to take just 10 milliseconds and there are 1000 concurrent connections, it will take 10 seconds to finish all of them. It’s pretty bad response time, isn’t it?

For this reason, Node is more useful as intelligent proxy and not real application server.

Other server solutions use different approach. They will spawn new thread or use thread pool for processing requests. On modern servers, it’s no problem to run hundreds of threads concurrently. The same situation as above with just a thread pool of 100 threads would mean that processing all of them take like 100 ms.

# Encryption vs hashing vs encoding

Encryption, hashing, and encoding are all techniques used in computer science and security, but they serve different purposes and operate in different ways:

1. <h3>Encryption:</h3>

- Encryption is the process of converting data into a ciphertext, which is an unreadable format, using an algorithm and a key.
- The purpose of encryption is to protect the confidentiality of data by making it unreadable to anyone who does not have the decryption key.
- Encryption is reversible, meaning the ciphertext can be decrypted back into its original form using the decryption key.
- Example encryption algorithms include AES (Advanced Encryption Standard) and RSA (Rivest-Shamir-Adleman).

2. <h3>Hashing:</h3>

- Hashing is the process of converting data of arbitrary size into a fixed-size hash value using a hashing algorithm.
- The key difference from encryption is that hashing is a one-way function; the original data cannot be derived from the hash value.
- Hash functions produce a unique hash value for a given input, but different inputs can produce the same hash value (known as a collision).
- Hashing is commonly used for data integrity verification, password storage, and indexing.
- Popular hashing algorithms include MD5, SHA-1, and SHA-256.

3. <h3>Encoding:</h3>

- Encoding is the process of converting data from one format to another, often for the purpose of transmission or storage.
- Unlike encryption and hashing, encoding does not provide security; it's meant to represent data in a different format that is easily translatable.
- Encoding schemes include ASCII, Unicode, Base64, and URL encoding.
- Encoded data can be easily decoded back into its original form, as the process is reversible.

In summary, encryption is used for securing data by converting it into an unreadable format, hashing is used for data integrity verification and irreversible transformation, and encoding is used for representing data in a different format for transmission or storage. Each serves distinct purposes in computer science and security.

# readFile vs readline vs createReadStream

In Node.js, <b>readFile</b>, <b>readline</b>, and <b>createReadStream</b> are all methods used for reading data from files, but they serve different purposes and operate in different ways:

1. <h3>readFile:</h3> 

- readFile is a method provided by the <b>fs</b> (file system) module in Node.js.
- It is used to asynchronously read the entire contents of a file.
- It reads the entire file into memory and returns the contents as a buffer or string, depending on the specified encoding.
- Useful for small to medium-sized files where you need to read the entire contents at once.

Example:

```javascript
const fs = require('fs');

fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) throw err;
  console.log(data);
});
```

2. <h3>readline</h3> 

- readline is a module in Node.js that provides an interface for reading data from a readable stream (like a file) line-by-line.
- It's particularly useful for processing large files or streams where loading the entire file into memory would be inefficient or impractical.
- readline provides methods such as <b>createInterface()</b> to create an instance of the interface and <b>on('line')</b> event to handle each line of data.

Example:

```javascript
const readline = require('readline');
const fs = require('fs');

const rl = readline.createInterface({
  input: fs.createReadStream('example.txt'),
  output: process.stdout,
  terminal: false
});

rl.on('line', line => {
  console.log(line);
});
```

3. <h3>createReadStream</h3> 

- createReadStream is a method provided by the fs module in Node.js.
- It's used to create a readable stream to read data from a file.
- Unlike <b>readFile</b>, which reads the entire file into memory, <b>createReadStream</b> reads data from the file in chunks as needed, making it more memory-efficient for large files.

Example:

```javascript
const fs = require('fs');

const stream = fs.createReadStream('example.txt', 'utf8');

stream.on('data', chunk => {
  console.log(chunk);
});

stream.on('end', () => {
  console.log('File reading completed.');
});
```

In summary, <b>readFile</b> is used for reading entire file contents into memory, <b>readline</b> is used for efficiently reading large files line-by-line, and <b>createReadStream</b> is used for reading large files in chunks as a stream. Choose the appropriate method based on your specific use case and the size of the file you're working with.

# Streams and Buffer in Node.Js

1. <h3>Buffer:</h3>

- A buffer is a temporary storage area in memory used to hold data while it's being transferred between two locations or processed.
- In Node.js, buffers are instances of the Buffer class, which provides a way to work with binary data directly.
- Buffers are useful when dealing with binary data, such as reading from or writing to files, network communication, or cryptographic operations.
- You can create a buffer from strings, arrays, or directly from memory.
  
Example:

``` javascript
const buffer = Buffer.from('Hello', 'utf8');
console.log(buffer); // <Buffer 48 65 6c 6c 6f>
```

2. <h3>Stream:</h3>

- A stream is a continuous flow of data that is read from or written to sequentially.
- In Node.js, streams are instances of the Stream class and its subclasses (<b>Readable</b>, <b>Writable</b>, <b>Duplex</b>, and <b>Transform</b>).
- Streams are useful for processing large amounts of data in smaller, manageable chunks, which can improve performance and memory efficiency.
- There are different types of streams:
  - Readable streams: Used for reading data from a source (e.g., file, network).
  - Writable streams: Used for writing data to a destination (e.g., file, network).
  - Duplex streams: Both readable and writable, allowing for bidirectional communication.
  - Transform streams: A special type of duplex stream that can modify or transform the data as it's being read or written.
- Example (creating a readable stream and piping it to a writable stream):

``` javascript
const fs = require('fs');

const readableStream = fs.createReadStream('input.txt');
const writableStream = fs.createWriteStream('output.txt');

readableStream.pipe(writableStream);
```

In summary, buffers are used to work with binary data directly in memory, while streams are used for reading from or writing to data sources in a sequential and efficient manner. Both are essential for handling data in Node.js, especially when dealing with large datasets or asynchronous operations.
