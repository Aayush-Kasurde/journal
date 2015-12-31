Firewalld
=========


* Adding port permanently in firewalld config ::

    $ sudo firewall-cmd --zone=public --add=24800/tcp

* List all ports ::

    $ sudo firewall-cmd --zone=public --list-ports

* List all services ::

    $ sudo firewall-cmd --zone=internal --list-services
