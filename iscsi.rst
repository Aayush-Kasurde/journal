iSCSI
=====

* Install iscsi package ::

		$ yum install iscsi-initiator-utils

* Query iscsi-initiator package installed or not :: 
	
		$ rpm -qa | grep -i iscsi

* Query iscsi intiator name ::
	
		$ cat /etc/iscsi/initiatorname.iscsi 
	
  This will return output like 
  `InitiatorName=iqn.1994-05.com.redhat:9f51e9794fa`

* Start the iscsi service ::

		$ service iscsi start 

  or ::

		$ /etc/init.d/iscsi start

* Discover available targets from a discovery portal ::

        $ iscsiadm -m discovery -t sendtargets -p ipaddress

* Log into all targets :: 
	
		$ iscsiadm –m node –l

* To see the connection status :: 
	
		$ iscsiadm -m session

* Login individual target :: 
	
		$ iscsiadm -m node -l -T <iqn_of_target> -l -p <target_ip_address>:3260

  e.g., `iscsiadm -m node -l -T iqn.2001-05.com.equallogic:0-8a0906-centos-cluster -l -p 192.168.40.10:3260`

* Logging out all targets :: 
	
		$ iscsiadm –m node –u

* Logging off an individual target :: 
	
		$ iscsiadm –m node –u –T <iqn_of_target> –p <target_ip_address>:3260

  e.g., `iscsiadm –m node –u –T iqn.2001-05.com.equallogic:0-8a0906-centos-cluster –p 192.168.40.10:3260`

* Delete session records :: 
	
		$ iscsiadm –o delete

* Rescan lun :: 

		$ iscsiadm -m node -p <target_ip_address> --rescan

* Get the WWN of the fiber card port(s) by showing the content of `/sys/class/fc_host/hostX/port_name` ::

		$ cat /sys/class/fc_host/hostX/port_name

* Rescan iscsi devices :: 
        
        $ for i in `ls -U /sys/class/scsi_host/`; do  echo "- - -" > /sys/class/scsi_host/$i/scan ;  done

* See iscsi devices :: 
        
        $ cat /proc/scsi/scsi

* Rescan FC devices :: 
        
        $ for i in `ls -U /sys/class/fc_host/`; do echo 1 > /sys/class/fc_host/host$i/issue_lip; done

* View iSCSI database regarding discovery ::

        $ iscsiadm -m discovery -o show


* View iSCSI database regarding targets to log into ::

        $ iscsiadm -m node -o show


* View iSCSI database regarding sessions logged into ::

        $ iscsiadm -m session -o show