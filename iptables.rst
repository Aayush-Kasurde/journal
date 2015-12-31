iptables
========


* Unblock specific port in iptables ::

    $ iptables -I INPUT -p tcp --dport 80 -j ACCEPT

* Delete single iptables rule ::

    $ iptables -D INPUT -p tcp --dport 80 -j ACCEPT

* Delete single iptables rule using chain number ::

    $ iptables -D INPUT 4
