Journalctl
==========


* View logs of crontab using journalctl ::

    $  journalctl _COMM=crond --since "10:00" --until "11:00"


* View sshd logs using journalctl :: 
    
    $ journalctl _COMM=sshd


* View yesterday's log ::

    $ journalctl --yesterday


* View all logs from yesterday ::

    $ journalctl --since "2015-10-10" --until "2015-01-11"
