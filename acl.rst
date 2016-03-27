ACL
===


* Private directory for User ::

  # setfacl -m user::rwx,group::---,other::---,user:billy:r-x foo
