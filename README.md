# useful-commands
This repository contains some useful commands.

# Java Debugger
This is the basic usage of the **jdb**, which may be used if no source code is available, or it is difficult to import the Java project into IDE, making debugging in IDE difficult. If JDK is installed, the **jdb** should be available.

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

**Basic commands**
* help - print all commands
* cont - continue execution
* stop at \<class>:\<line> - set breakpoint at a line of a class
* stop in \<class>.\<method|variable> - set breakpoint at a method or a variable of a class
* catch \<exception> - set exception breakpoint
* clear - list all breakpoints
* clear \<breakpoint> - remove a breakpoint
* step over - step to the next line
* step into - step into the next executing method
* step out - step outside of the current method
* list - print current source code context
* where - print the current stack
* threads - print all the threads
* thread - print the current thread

# Maven
Some commonly used Maven commands (plugins, goals etc.)

**Use sepcific files**

	mvn -f <another_pom> -s <another_settings> <goal|phase|lifecycle>

**Find available goals of a plugin**

	mvn help:describe -Dplugin=compiler
	mvn help:describe -Dplugin=compiler -Ddetail

**List dependencies**

	mvn dependency:tree

**Download a dependency**

	mvn dependency:copy -Dartifact=<group_id>:<artifact_id>:<version> -DoutputDirectory=<download_dir>
