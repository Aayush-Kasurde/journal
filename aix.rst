AIX  
===

* Reset the NIM client machine state from NIM server ::
        
        # nim -Fo reset <hostname> 
 
  **Usage**: $ nim -Fo reset dbaix1-v8

	     This is will reset NIM client dbaix1-v8 to ready state 

* Deallocate resources from NIM client from NIM server ::

        # nim -Fo deallocate -a lpp_source=LPP_61TL7SP5 dbaix2-v10 

* Remove NIM client from NIM server:: 

        # nim -Fo remove <hostname> 

* List down all NIM client form NIM server ::

        # lsnim -l 

* List down properties of particular NIM client from NIM server ::

        # lsnim -l <hostname> 

* Change file system size ::
        
        # chfs -a size=+1G /opt

  or ::

        # chfs -a size=-1G /opt

* List Fibre Card adapter ::
	
		# lsdev -Cc <adapter_name>

* Get Fibre Card WWPN number ::
	
		# lscfg -v1 <adapter_name>

* Get statistics for Fibre Card adapter ::
	
		# fcstat <adapter_name>

