gnu-screen
==========

All commands are inside screen 

* Open new window ::
        
        #  Ctrl + a + c 

* Close windows in screen :: 

	# Ctrl + a + k 

* Detaching the screen (Coming to normal non-screen window) :: 

	# Ctrl + a + d 

* Reattaching the screen :: 

	$ screen -R 

* Goto next windows :: 

	# Ctrl + a + n 

* Goto previous windows :: 
	
	# Ctrl + a + p 

* Show list of windows :: 

	# Ctrl + a + Shift + " 

* Split panes :: 
	
	# Ctrl + a + Shift + s 

* Toggle between split panes :: 

	# Ctrl + a + Tab 

* Closing split panes :: 

	# Ctrl + a + Shift + x 

* Locking the screen ::

	# Ctrl + a + x  (Enter password for locking and unlocking)

* Fancy hardstatus :: 
	
	# vi /etc/screenrc 
	hardstatus on
	hardstatus alwayslastline
	hardstatus string "%{.bW}%-w%{.rW}%n %t%{-}%+w %=%{..G} %H %{..Y} %m/%d %C%a "


