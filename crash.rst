crash
=====

* Start crash :: 

        # crash /var/crash/timestamp/vmcore /usr/lib/debug/lib/modules/kernel/vmlinux

* Displaying the Message Buffer :: 
        
        crash> log

* Displaying a Backtrace :: 
        
        crash> bt <PID>

* Displaying a Process Status :: 
        
        crash> ps 

* Displaying Virtual Memory Information ::
        
        crash> vm <PID>

* Displaying Open Files ::
        
        crash> files

* Exiting the Utility ::
        
        crash> exit
