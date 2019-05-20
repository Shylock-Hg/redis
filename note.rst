My note of Redis
==================

Flow
--------

1. Initialize the server configuration from `command line arguments`,
`defualt configuration`, `configuration file` and `environment variables`.

2. Create Event Loop, create servers (create socket and listen to specific
port), and create Events (register fd and events).

3. Loop: Pool the Event Loop fd, handle the events (accept connections and
create clients), BeforeSleep (handle the clients), AfterSleep (acquire the GIL
for global context)

4. NIO jobs: do the file closing, AOF flushing and resources releasing in
background threads.
