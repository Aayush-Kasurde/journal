LDAP
=====


* Get default naming context :: 
        
        $ /usr/bin/ldapsearch -x -b "" -s base defaultnamingcontext | grep -i 'defaultnamingcontext: ' | awk '{print $2}'

* Search ACI ::
    
        $ ldapsearch -h localhost -p 389 -D "cn=directory manager" -w Secret123 -b "dc=testrelm,dc=test" aci 
