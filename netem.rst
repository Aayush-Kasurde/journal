netem
=====

Netem provides Network Emulation functionality for testing protocols by emulating the properties of wide area networks.


* Adding fixed amount of delay to packets going out of the Ethernet::

        # tc qdisc add dev eth0 root netem delay 100ms

* Adding random amount of variation in delay to packets going out of the Ethernet::

        # tc qdisc add dev eth0 root netem delay 100ms 10ms

* Adding random amount of variation in delay with correlation to packets going out of the Ethernet::

        # tc qdisc add dev eth0 root netem delay 100ms 10ms 25%

  This causes the added delay to be 100ms ± 10ms with the next random element depending 25% on the last one.

* Specify non-uniform distribution in delay ::

        # tc qdisc add dev eth0 root netem delay 100ms 20ms distribution normal

  distribution value : (normal, pareto, paretonormal)
