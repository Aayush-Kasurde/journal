GDB
====

* Start gdb using program ::
        
        $ gdb program

* Start gdb using core file :: 
        
        $ gdb program core 

* Start gdb using process ID :: 
        
        $ gdb program <PID>

* Quitting from gdb :: 

        (gdb) quit

* Running shell command from gdb prompt ::
        
        (gdb) shell ls

* Invoke make from gdb prompt ::

        (gdb) make make-args
