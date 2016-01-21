LDAP
=====


* Get default naming context ::

    $ /usr/bin/ldapsearch -x -b "" -s base defaultnamingcontext | grep -i 'defaultnamingcontext: ' | awk '{print $2}'

* Search ACI ::

    $ /usr/bin/ldapsearch -h localhost -p 389 -D "cn=directory manager" -w Secret123 -b "dc=testrelm,dc=test" aci

* Search onelevel ::

    $ /usr/bin/ldapsearch -h $HOSTNAME -b "dc=example,dc=com" -s one -x -w Secret123

* Search Subtree ::

    $ /usr/bin/ldapsearch -h $HOSTNAME -b "dc=example,dc=com" -s sub -x -w Secret123

* Search base ::

    $ /usr/bin/ldapsearch -h $HOSTNAME -b "dc=example,dc=com" -s base -x -w Secret123

* Modifying entry using command ::

    $ /usr/bin/ldapmodify -a -x -h $HOSTNAME -p 389 -D "cn=Directory Manager" -w Secret123 -c -f ./subtree.ldif

* Configuring SSSD for using LDAP ::

   $ authconfig \
   --enablesssd \
   --enablesssdauth \
   --enablelocauthorize \
   --enableldap \
   --enableldapauth \
   --ldapserver=ldap://<ldap_api_address>:389 \
   --enableldaptls \
   --ldapbasedn=dc=testrelm,dc=test \
   --enablerfc2307bis \
   --enablemkhomedir \
   --enablecachecreds \
   --update
