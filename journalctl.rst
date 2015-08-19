Journalctl
==========


* View logs of crontab using journalctl ::

    $  journalctl _COMM=crond --since "10:00" --until "11:00"


* View sshd logs using journalctl :: 
    
    $ journalctl _COMM=sshd
