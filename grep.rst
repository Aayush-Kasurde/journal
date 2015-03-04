grep  
====

* Search file for keyword `Error`::

        $ grep "Error" mylogfile.log 

* Search file for keyword `Error` with case-insensitivity ::

        $ grep -i "error" mylogfile.log 

* Searching several words in file ::

        $ grep -Ei "error|exception|fatal" mylogfile.log 


* See more after and more before keyword in file::

        $ grep -A 10 -B 20 "exception" mylogfile.log 

  **Usage**: Above grep will show 10 line after and 20 line before `exception` word in `mylogfile.log` 

* Search file and line with filename::

        $ grep -nrH MyMethodName * 

  **Usage**: Above grep command will search files in current directory recursively with line and filename.

* Search keyword in file and print only filename::

        $ grep -ril <keyword> <location>

  **Usage**: `grep -ril "*myword*"` 

* Find keyword in file and print filename only ::

	grep -l "word" * 


