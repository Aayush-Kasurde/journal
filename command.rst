At Shell Prompt
=================

* Running previous command with sudo ::

   	$ ls -la
   	$ sudo !!

    **Usage**: This will run `ls -la` command using sudo command

* Using !! on shell prompt ::

   	$ ls -la a  && echo !!:2

    **Usage**: This will print a on screen.

* Finding top 5 largest files in directory ::

   	$ ls -lSh . | head -5

* Finding top 5 smallest files in directory ::

   	$ ls -lSr . | head -5

* Finding top 10 directories in / ::

   	$ du -a /var | sort -n -r | head -n 10

* Finding top directories in / ::

   	$ du -ch --max-depth 1 /

* Using !! to replace some part of command ::

   	$ echo "foo"
   	$ !!:gs/foo/bar

    **Usage**: Runs previous command replacing foo by bar every time that foo appears

* Using !$,  !^,  !* ::

   	$ echo foo bar baz
   	$ echo !$ # will return baz
   	$ echo !^ # will return foo
   	$ echo !* # will return foo bar baz

* Press ESC + . to copy last argument of bash command ::

   	$ cp file /to/some/path
   	$ cd [ESC + . ] # This will take you to /to/some/path

* Tail to dmesg ::

   	$ watch 'dmesg | tail -10'

* To determine if you have a process holding an unlinked file open ::

   	$ lsof -a +L1 <path_of_directory>

       or

	$ lsof +D +L1 <path_of_directory>

* Find the directory which takes highest space in root ::

   	$ du --max-depth=1 -h

* Report XSI interprocess communication facilities status::

   	$ ipcs -s # for seamphore
   	$ ipcs -q # for message queues
   	$ ipcs -m # for shared memory segments

* Delete till last word in command prompt::

   	CRTL + w

* Go to start of line in command prompt ::

    CTRL + a

* Delete single word on command prompt ::

    ALT + BACKSPACE

* Ask Linux to rescan the SCSI devices on that FC HBA::

    $ echo - - - >/sys/class/scsi_host/host$NUMBER/scan

    **Usage**: The wildcards “- - -” mean to look at every channel, every target, every LUN.

* Taking diff of directory::

    $ diff -bur <directory_2> <directory_1>

* Executing multiple commands using xargs ::

    $ echo 1 | xargs -I{} sh -c "echo {} && echo {}"

    **Usage**: Here xargs will take arguments in {},  replace {} in next shell prompt

* Force running logrotate configuration file::

    $ logrotate --force /etc/logrotate.d/nginx

* Check permissions of file or directory ::

    $ stat /var/lib/kdcproxy| sed -n '/^Access: (/{s/Access: (\([0-9]\+\).*$/\1/;p}'

Networking

*	Shows the network connections ::

    $ ifconfig

* Show ip address for all available interfaces ::

    $ ip addr | grep inet

* Find which process owns port number::

    $ fuser -v -n tcp <port_number>

    **Usage**: fuser -v -n tcp 6000

* List used ports ::

    $ lsof -i <protocol>:<port>;

    **Usage**: lsof -i tcp:80

    check is apache reading 80 or not

* Get blocks and partitions ::

    $ egrep -v "#blocks|^$" /proc/partitions|awk '{print $3,  $4}'

Swap

* More swap with a swap file::

   	$ dd if=/dev/zero of=/swapfile bs=1024 count=65536 #Create 64MB swap file on your root partition
   	$ mkswap /swapfile 65536          #convert file to swap file
   	$ sync
   	$ swapon /swapfile        #add swapfile to your swapspace

dd

* Create file of 1 TB file with 8192 blocksize::

   	$ dd if=/dev/zero of=/mnt/disk8 bs=8192 seek=134217728 count=0

curl

* Post data using curl::

	$ curl http://10.209.103.136:443 -d 'hostname=blah' -X POST -v
