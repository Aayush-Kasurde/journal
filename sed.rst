sed 
===

* Match whole string::
	
		$ sed "s/\b<keyword\b/g"

  **Usage**: echo "bar foobar" | sed "s/\\bbar\\b/no\ bar/g"

* Print line matching given pattern::

        $ sed -n /PATTERN/p filename


* Prints lines matching given pattern till address::

        $ sed -n ‘/PATTERN/,Np’ filename


* Prints lines matching given address till pattern::

        $ sed -n ‘N,/PATTERN/p’ filename


* Prints from the line matches the given pattern to end of file::

        $ sed -n ‘/PATTERN/,$p’ filename


* Prints the lines which matches the pattern and next N lines following the matched line::

        $ sed -n ‘/PATTERN/,+Np’ filename

