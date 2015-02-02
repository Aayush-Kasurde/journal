PS
==

* Kill all process using string::

    	$ ps -ef | grep PROCESS | grep -v grep | awk '{print $2}' | xargs kill -9

    **Usage**: Kills all PIDs matching the search term of “PROCESS”. Be careful what you wish for :)

* Find information about process by name::

    	$ ps ax | grep <process_name>
    	$ ps ax | grep <process_name> | grep -v grep

    **Usage**:

        ps ax | grep apache2
        ps ax | grep [Aa]pache2 #This will only show apache process (without grep)
        ps ax | grep apache2 | grep -v grep

* Kill pts::

    	$ ps -t pts/1 | awk '/[0-9]/ {print $1}' | xargs sudo kill -9
