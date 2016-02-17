iptables
========


* Unblock specific port in iptables ::

    $ iptables -I INPUT -p tcp --dport 80 -j ACCEPT

* Delete single iptables rule ::

    $ iptables -D INPUT -p tcp --dport 80 -j ACCEPT

* Delete single iptables rule using chain number ::

    $ iptables -D INPUT 4

* Allow HTTP traffic ::

    $ iptables -A INPUT -p tcp -m tcp --sport 80 -j ACCEPT
    $ iptables -A OUTPUT -p tcp -m tcp --dport 80 -j ACCEPT
    $ iptables -A INPUT -p tcp -m tcp --sport 443 -j ACCEPT
    $ iptables -A OUTPUT -p tcp -m tcp --dport 443 -j ACCEPT

* Allow SSH traffic ::

    $ iptables -A INPUT -p tcp --dport 22 -j ACCEPT
    $ iptables -A OUTPUT -p udp --sport 22 -j ACCEPT

