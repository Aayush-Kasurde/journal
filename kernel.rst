Linux Kernel
============

* Shows the status of modules in the Linux Kernel::

    	$ lsmod

* Shows the list of modules for Linux Kernel::

    	$ ls /lib/modules/$(uname -r) -R  | grep ko

* Finding hardware information::

    	$ lshw

    **Usage**: `lshw -c video` #This will provide information about video hardware.


* Show information about particular module::

    	$ modinfo <driver_name>

    **Usage** : `modinfo nvidia` #This will provide information about nvidia driver