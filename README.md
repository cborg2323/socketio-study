# Socket.IO tutorial

## Integrating Socket.IO
Socket.IO is composed of two parts:
- A server that integrates with (or mounts on) the Node.JS HTTP Server (the socket.io package)
- A client library that loads on the browser side (the socket.io-client package)

## Emitting events
The main idea behind Socket.IO is that you can send and receive any events you want, with any data you want.

You can send any data to the other side with socket.emit(). You can send any number of arguments, and all serializable data structures are supported, including binary objects.

## Broadcasting
In order to send an event to everyone, Socket.IO gives us the io.emit() method.

If you want to send a message to everyone except for a certain emitting socket, we have the broadcast flag for emitting from that socket.

## Rooms
In Socket.IO jargon, a room is an arbitrary channel that sockets can join and leave. It can be used to broadcast events to a subset of connected clients.

## Acknowledgements
Events are great, but in some cases you may want a more classic request-response API. In Socket.IO, this feature is named "acknowledgements". It comes in two flavors:

### With a callback function
You can add a callback as the last argument of the emit(), and this callback will be called once the other side has acknowledged the event.

### With a Promise
The emitWithAck() method provides the same functionality, but returns a Promise which will resolve once the other side acknowledges the event.
