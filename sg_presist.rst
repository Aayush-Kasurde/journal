sg_presist
==========

* To query all registrant keys for given device ::

        $ sg_persist -i -k -d /dev/sdd

* To query all reservations for given device ::

        $ sg_persist -i -r -d /dev/sdd

* To register key :: 

        $ sg_persist -o -G -S 123abc /dev/sdd

* To clear all registrants ::

        $ sg_persist -C -K 123abc -o -d /dev/sdd

* To reserve ::
        
        $ sg_persist -o -R -K 123abc -T 5 -d /dev/sdd

* To release :: 

        $ sg_persist -o -L -K 123abc -T 5 -d /dev/sdd

  Common used reservation Types

  - 5 - Write Exclusive, registrants only
  - 6 - Exclusive Access, registrants only 