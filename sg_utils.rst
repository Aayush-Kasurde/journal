sg_utils
========

* Query on page 83 for information :: 
	
	# sg_inq --vpd --page=0x83 <block_device>

  e.g., sg_inq --vpd --page=0x83 /dev/sdi

* Query for mode sense pages ::
        
         # sg_modes --all <block_device>
    
  e.g., sg_modes --all /dev/sdi

* Fetch the number of blocks and the individual block size for disks :: 

        # sg_readcap <block_device> 

  e.g., sg_readcap <block_device>

* Send write same command :: 
    
        # sg_write_same --16 --lba=<logical_block_address> <block_device>
    
  e.g., sg_write_same --16 --lba=0 /dev/sdc
