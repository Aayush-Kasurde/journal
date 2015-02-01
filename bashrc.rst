Bashrc
========

* Function to add alias of command::

        function addalias(){
           echo -e "adding alias $1 for $2\n"
           echo -e "alias ${1}=\"${2}\"" >> ~/.bashrc
           . ~/.bashrc
        }

        
  **Usage** : `addalias  nameofalias "command"` 


* Function to find newly installed python module working::
        
        function import(){
           python -c "import ${1}" 2> /dev/null 
           [ $? -eq 0 ] && echo -e "Python module ${1} installed properly" || \
           echo -e "Python module ${1} is missing or perhaps mispelled" 
        }


  **Usage** : `import python_modulename`

* Function to mkdir and cd into directory:: 

        function mkcd () {
          mkdir -p "$@" && eval cd "\"\$$#\"";
        }

  **Usage** : `mkcd abc` 

* Function to show IP of all connections ::

		function ips () {
	    		local interface=""
	    		local types='vmnet|en|eth|vboxnet|wlan|wl|tap|tun'
	    		local i
				for i in $(
					ifconfig \
	       		    | egrep -o '(^('$types')[0-9]|inet (addr:)?([0-9]+\.){3}[0-9]+)' \
	           	    | egrep -o '(^('$types')[0-9]|([0-9]+\.){3}[0-9]+)' \
	                | grep -v 127.0.0.1
				); do
				if ! [ "$( echo $i | perl -pi -e 's/([0-9]+\.){3}[0-9]+//g' )" == "" ]; then
					interface="$i":
				else
					echo $interface $i
				fi
				done
		}
	
  **Usage**: `ips` 
  
* Function to check "Are you root ?":: 

		chk_root () {  
			if [ ! $( id -u ) -eq 0 ]; then  
				echo -e "Must be run as root"  
				exit  
			fi  
		}  

  **Usage**: Just use `chk_root` in script
