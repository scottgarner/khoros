# Khoros

Khoros is a simple platform for sending and receiving arbitrary data through socket.io.

### Philosophy

The aim of Khoros is to allow for complex networked interactions without worrying about server logic. 

### Architecture

Khoros adopts the concept of rooms from socket.io, a room simply being a collection of users. When initializing Khoros, you specify both a room to sing (broadcast) to and a room to listen to. Depending on your use case, these rooms may or may not be the same and in many cases one or the other will be null.

### Use Cases

* Many to Many

	By specifying the same room for both singing and listening, you can create many-to-many experiences. Singers do not hear their own songs. 

* One to Many

	This use case is ideal for a scenario with a performer and an audience. In the performer application, specify only room for singing. In the audience application, specify that same room for listening.

* Many to One

	To allow multiple users to interact with a single application, specify a singing room for the participants and have the central client application listen to only that room.

### Projects

The pieces of Khoros are broken into individual repositories.

* [khoros](http://github.com/scottgarner/khoros)

	This is the main project repository for documentation and reference.

* [khoros-server](http://github.com/scottgarner/khoros-server)

	This is an example server build for heroku using the middleware below.

* [khoros-middleware](http://github.com/scottgarner/khoros-middleware)

	This is middleware for socket.io to allow for the automatic routing of events based on rooms.

* [khoros-client](http://github.com/scottgarner/khoros-client)

	This is a javascritpt implementation of Khoros, which can be served automatically by the middleware.

* [khoros-unity](http://github.com/scottgarner/khoros-unity)

	This is a simple implementation for Khoros for Unity along with some examples.
