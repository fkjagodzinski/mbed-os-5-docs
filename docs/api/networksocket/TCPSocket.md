## TCPSocket

<span class="images">![](http://os-doc-builder.test.mbed.com/docs/development/mbed-os-api-doxy/class_t_c_p_socket.png)<span>TCPSocket class hierarchy</span></span>

The TCPSocket class provides the ability to send a stream of data over TCP. TCPSockets maintain a stateful connection that starts with the `connect` member function. After successfully connecting to a server, you can use the `send` and `recv` member functions to send and receive data (similar to writing or reading from a file).

The constructor takes in the NetworkStack pointer to open the socket on the specified NetworkInterface. If you do not pass in the constructor, then you must call `open` to initialize the socket.

### Server socket

You can also use TCP to listen to incoming connections. To do this:

1. Bind socket to specific port by calling `TCPSocket::bind()`.
1. Set socket to listening mode by calling `TCPSocket::listen()`.
1. Accept incoming connection by calling `TCPSocket::accept()`.

Accepting a new connection returns a pointer to a new `Socket` object that you can use to communicate with the connected peer. Afterward, call this socket's `close()` function to shut down the connection and clean up the reserved resources.

Accepting a connection leaves the original socket in listening mode. You can continue to accept new connections until you destroy the listening socket, or call its `close()` method.

### TCPSocket class reference

[![View code](https://www.mbed.com/embed/?type=library)](http://os-doc-builder.test.mbed.com/docs/development/mbed-os-api-doxy/class_t_c_p_socket.html)

### TCPSocket Example

Here is a client example of HTTP transaction over TCPSocket:

[![View code](https://www.mbed.com/embed/?url=https://github.com/ARMmbed/mbed-os-example-sockets)](https://github.com/ARMmbed/mbed-os-example-sockets/blob/master/main.cpp)

### Related content

- [Socket](socket.html) API reference.
- [Cellular TCP sockets example](/docs/development/tutorials/cellular-tcp-sockets.html).
