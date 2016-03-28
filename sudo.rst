sudo
====


* Enable default logging for sudo command ::

    $ visudo # and add following line 
    
    Defaults logfile=/var/log/sudo.log
