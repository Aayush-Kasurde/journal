LDAP
=====


* Get default naming context :: 
        
        $ /usr/bin/ldapsearch -x -b "" -s base defaultnamingcontext | grep -i 'defaultnamingcontext: ' | awk '{print $2}'
