Processing Commands
The interpreter uses a loop to read all lines from its input, parse them, and then dispatch the command to an appropriate command handler. Input lines are parsed into two parts. The command, and any other text on the line. If the user enters a command foo bar, and your class includes a method named do_foo(), it is called with "bar" as the only argument.
The end-of-file marker is dispatched to do_EOF(). If a command handler returns a true value, the program will exit cleanly. So to give a clean way to exit your interpreter, make sure to implement do_EOF() and have it return True.
This simple example program supports the “greet” command:
Command arguments
This version of the example includes a few enhancements to eliminate some of the annoyances and add help for the greet command.
Live Help

In the previous example, the formatting of the help text leaves something to be desired. Since it comes from the docstring, it retains the indentation from our source. We could edit the source to remove the extra white-space, but that would leave our application looking poorly formatted. An alternative solution is to implement a help handler for the greet command, named help_greet(). When present, the help handler is called on to produce help text for the named command.
