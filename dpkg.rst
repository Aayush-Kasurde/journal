dpkg
=====

Quick cheat sheet you will find handy while using dpkg at shell prompt:

* Installing deb file using dpkg::

        dpkg -i <package_name>.deb

  **Usage**: `dpkg -i apache2_2.2.17-1ubuntu1.5_i386.deb`

* Installing deb packages recursively from given directory::

	dpkg -R <path_to_directory>

  **Usage**: `dpkg -R /var/cache/apt/archives/`

* Find all files related to package::
        
        dpkg -L <package_name>

  **Usage**: `dpkg -L apache2`

* List all package by name::
        
        dpkg -l | grep <package_name>

  **Usage**: `dpkg -l | grep apache2`

* Find which package is related to particular file::
        
        dpkg -S <file_name>

  **Usage**: `dpkg -S /etc/apache2/apache2.conf`

* Find status of package::
	
	dpkg -s <package_name> | grep Status 

  **Usage**: `dpkg -s apache2 | grep Status`

* Display details about package package group, version, maintainer, Architecture, display depends packages, description etc.::

	dpkg -p <package_name>

  **Usage**: `dpkg -p apache2`

* List files provided by given package::

	dpkg -c <deb_package_name>

  **Usage**: `dpkg -c apache2_2.2.17-1ubuntu1.5_i386.deb`

* List individual package name installed with short description::

	dpkg -l <package_name>

  **Usage**: `dpkg -l apache2`

* List all package name installed with short description::

	dpkg -l 

  **Usage**: `dpkg -l`

* Remove pacakge::

	dpkg -r <package_name>

  **Usage**: `dpkg -r apache2`

* Remove package with all configuration:: 

	dpkg -P <package_name>

  **Usage**: `dpkg -P apache2`

