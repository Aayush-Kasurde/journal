Find 
====

* Find files with particular word in its name::

        find <location> -iname <word> 

  **Usage** : `find /etc -iname "*apache*"`

* Find files with size more than certain size::

        find <location> -type f -size +<size_integer>M 

  **Usage** : `find / -type f -size +100M`

* Find files which are not modified in last x number of days:: 

        find <location> -mtime +<integer>

  **Usage** : `find . -mtime +2` #Find files in current dir which are not modified last 2 days 

        
* Find files which are modified in last x number of days:: 

        find <location> -mtime -<integer>

  **Usage** : `find . -mtime -2` #Find files in current dir which are modified last 2 days 

* Finding image files in current directory on the basis of mime-type::

		find . -type f -exec file {} \+ | grep -c -i 'image' 

  is faster than::

		find . -type f -print0 | xargs -0 file -i | grep -i image | wc -l

* Finding files which are newer than a particular file::

        find -newer vila_Fri_Mar_1_15:20:49_IST_2013.log -type f




