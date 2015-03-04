YUM
===

* Install a package :: 
        
        $  yum install <package_name>

* Remove a package :: 
        
        $  yum remove <package_name> 

* Update a package :: 
        
        $  yum update <package_name> 

* Search for a package :: 
        
        $  yum search <package_name> 

* Find information about a package ::
        
        $  yum info <package_name> 

* List packages containing a certain term :: 
        
        $  yum list <package_name> or <word_to_search> 

* Find what package provides a particular file :: 
        
        $  yum whatprovides </path/to/file>

* Update all installed packages ::
        
        $  yum -y update 

* Update a specific package :: 
        
        $  yum -y update <package_name>

* Install development packages :: 
        
        $  yum groupinstall "Development tools"
