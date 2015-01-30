Bash
====

* Compare integer in bash, unary operator expected error ::

	if [[ $i -ge 2 ]]

* Number tables :: 

        for i in {1..9}; do for j in $(seq 1 9); do echo -ne $i×$j=$((i*j))\\t;done; echo;done

* Test of variable is a number in bash :: 

        re='^[0-9]+$'
        if ! [[ $yournumber =~ $re ]] ; then
           echo "error: Not a number" >&2; exit 1
        fi
