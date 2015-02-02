proc
====

* View the different caches and their sizes::

    	$ sudo head -2 /proc/slabinfo; sudo cat /proc/slabinfo | egrep dentry\|inode

    Courtesy: http://linuxaria.com/howto/linux-memory-management

* Memory info::
        
        $ cat /proc/meminfo | head -2 

  High-Level Statistics
    
  * MemTotal: Total usable ram (i.e. physical ram minus a few reserved bits and the kernel binary code)
  * MemFree: Is sum of LowFree+HighFree (overall stat)
  * MemShared: 0; is here for compat reasons but always zero.
  * Buffers: Memory in buffer cache. mostly useless as metric nowadays
  * Cached: Memory in the pagecache (diskcache) minus SwapCache
  * SwapCache: Memory that once was swapped out,  is swapped back in but still also is in the swapfile (if memory is needed it doesn't need to be swapped out AGAIN because it is already in the swapfile. This saves I/O)



* Filesystem supported by running Kernel ::

        $ cat /proc/filesystems  

* CPU count ::
    
        $ cat /proc/cpuinfo | grep processor | wc -l  

* Command line provided to Linux Kernel at the time of booting ::

        $ cat /proc/cmdline 

* Uptime ::
    
        $ cat /proc/uptime 

* Get path of a process :: 
        
        $ ls -l /proc/$PID/exe

* Get memory mappings :: 
        
        $ cat /proc/iomem

* Get video memory size :: 
        
        $ cat /proc/iomem | grep -v "^ " | grep video

* Get name of exported symbols in kernel::

        $ cat /proc/kallsyms
        
  Here, Uppercase symbols are global/exported; lowercase are local unexported symbols.
    * D d The symbol is in the initialized data section.
    * S s The symbol is in an uninitialized data section for small objects.
    * T t The symbol is in the text (code) section.
