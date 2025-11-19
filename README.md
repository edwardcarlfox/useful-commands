# useful-commands
This repository contains some useful commands.

# Java Debugger

**Start application with debugging**
For Windows
	java -agentlib:jdwp=transport=dt_shmem,server=y,address=<port> <class>
For other systems
	java -agentlib:jdwp=transport=dt_socket,server=y,address=<port> <class>

**Attach to process**
For Windows
	jdb -connect com.sun.jdi.SocketAttach:hostname=<host>,port=<port>
For other systems
	jdb -attach <host>:<port>
