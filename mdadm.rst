mdadm
=====

* Create RAID using mdadm :: 

    $ mdadm --create --verbose /dev/md0 --level=1 /dev/sda1 /dev/sdb2

* Remove failed disk from RAID ::
    
    $ mdadm --remove /dev/md0 /dev/sda1

* Add a disk to an existing array :: 
    
    $ mdadm --add /dev/md0 /dev/sdb1

* Verifying the status of the RAID arrays ::
    
    $ mdadm --detail /dev/md0

* Stop RAID arrays ::
    
    $ mdadm --stop /dev/md0

* Start RAID arrays ::
    
    $ mdadm --start /dev/md0
