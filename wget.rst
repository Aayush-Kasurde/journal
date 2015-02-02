wget
====

* Download list of files using wget::

    	$ cat <file_containing_url> | xargs wget -c

    **Usage** : `cat urlist.txt | xargs wget -c` #download content of url for urlist.txt

* Download list of files using wget::

    	$ wget -i <file_containing_url>

* Passing post data using wget command::

    	$ wget --post-data "name=aayush" http://localhost/login.php

    **Usage** : Here login.php will contain code for processing post data