alias 
=====

Following are some alias to make you work faster 

* Alias for `cd` command:: 

        alias cd..="cd .."
        alias 2..="cd ../.."
        alias 3..="cd ../../.."
        alias 4..="cd ../../../.."
        alias 5..="cd ../../../../.."

* Alias for `apt-get` command:: 
	
		alias agi='apt-get install'
		alias agu='apt-get update'
		alias ags='apt-cache search'
		alias agsh='apt-cache show'
		alias agr='apt-get remove'
		alias agd='apt-get dist-upgrade'

* Alias for `ssh` command::

        alias dev="user@dev.example.com -p 8000"

* Alias for `df` command:: 
	
		alias df="df -TPh"

* Alias for Port usages::

		alias lsof="sudo lsof -i -P -sTCP:LISTEN"

