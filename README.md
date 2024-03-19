# What is Node.js?

Node.js is an open-source, cross-platform JavaScript runtime environment that executes JavaScript code outside a web browser.

<b>Note:</b> 
  - Node.js is not a programming language like Python, Java or C/C++. Node.js is a runtime, similar to Java virtual machine, that converts JavaScript code into machine code.
  - Node.js uses asynchronous programming!

# Why Node.js?

A common task for a web server can be to open a file on the server and return the content to the client.

Here is how PHP or ASP handles a file request:

1. Sends the task to the computer's file system.
2. Waits while the file system opens and reads the file.
3. Returns the content to the client.
4. Ready to handle the next request.
 
Here is how Node.js handles a file request:

1. Sends the task to the computer's file system.
2. Ready to handle the next request.
3. When the file system has opened and read the file, the server returns the content to the client.

Node.js eliminates the waiting, and simply continues with the next request.

Node.js runs single-threaded, non-blocking, asynchronous programming, which is very memory efficient.
___

1. <b>Real-time Applications:</b> Ideal for building real-time web applications like chat and live updates due to its event-driven nature.
2. <b>Unified JavaScript Development:</b> Use JavaScript for both server-side and client-side scripting, streamlining development processes.
3. <b>High Performance:</b> Leverages Google's V8 engine, allowing for fast code execution, particularly beneficial for I/O-heavy operations.
4. <b>Scalability:</b> Designed with scalability in mind, making it suitable for applications that need to scale horizontally or vertically.

<b>Features Of Node.js:</b>   

1. <b>Easy:</b> Node.js is quite easy to start with. It’s a go-to choice for web development beginners. With a lot of tutorials and a large community—getting started is very easy.
2. <b>Scalable:</b> It provides vast scalability for applications. Node.js, being single-threaded, is capable of handling a huge number of simultaneous connections with high throughput.
3. <b>Speed:</b> Non-blocking thread execution makes Node.js even faster and more efficient.
4. <b>Packages:</b> A vast set of open-source Node.js packages is available that can simplify your work. There are more than one million packages in the NPM ecosystem today.
5. <b>Strong:</b> backend—Node.js is written in C and C++, which makes it speedy and adds features like networking support.
6. <b>Multi-platform:</b> Cross-platform support allows you to create SaaS websites, desktop apps, and even mobile apps, all using Node.js.
7. <b>Maintainable:</b> Node.js is an easy choice for developers since both the frontend and backend can be managed with JavaScript as a single language.

# Applications of Node.js

Node.js is used for building different type of applications. Some of the application types are listed below −

1. <b>Streaming applications:</b> Node.js can easily handle real-time data streams, where it is required to download resources on-demand without overloading the server or the user’s local machine. Node.js can also provide quick data synchronization between the server and the client, which improves user experience by minimizing delays using the Node.js event loop.

2. <b>Single page apps:</b> Node.js is an excellent choice for SPAs because of its capability to efficiently handle asynchronous calls and heavy input/output(I/O) workloads. Data driven SPAs built with Express.js are fast, efficient and robust.

3. <b>Realtime applications:</b> Node.js is ideal for building lightweight real-time applications, like messaging apps interfaces, chatbots etc. Node.js has an event- based architecture, as a result has an excellent WebSocket support. It facilitates real-time two-way communication between the server and the client.

4. <b>APIs:</b> At the heart of Node.js is JavaScript. Hence, it becomes handling JSON data is easier. You can therefore build REST based APIs with Node.js
   
   
