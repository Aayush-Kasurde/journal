AWK
===

* Count number of lines in a file ::

		$ awk 'END { print NR }' <filename>

* Grep a pattern in line :: 
		
		$ echo "Abc123" | awk 'BEGIN {
			regex="[0-9]+" 
			}
		{
			if (match($1, regex)) { 
				pattern = substr($1, RSTART, RLENGTH)
			}
			print pattern	
		}'


* Ignore case in matching string like ```grep -i``` ::
	
		$ echo "caseless" | awk ' BEGIN { IGNORECASE=1; } /CASELESS/ { print }'

* Skip first and last column ::

        # awk '{$1="";$NF="";print}' <filename>
