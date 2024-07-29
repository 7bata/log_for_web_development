# Recording Date: 7/28/2024

1. #### Struggling setting up WordPress(Really a lot of chanllenges)
	
	##### Challenges:
	
	​	-Cannot Enter the Password when logging in  MySQL
	
	###### 	Solution: the password entered is invisible but you did enter the password already, just make sure you the password you entered is correct and press "Enter". If you successfully log in, it would inform you a successful message.
	
	​	-Cannot change nginx configuration via vim
	
	###### 	Solution: use \q to exit MySQL, you cannot find nginx configuration when you arre in the MySQL.
	
	​	-Cannot access my web by using Public Internet Protocol Address(Public IP)
	
	###### 	Solution: Add 80 port(for http) and 443 port(for https) in the Security Group of Alibaba Cloud Console
	
	​	-Cannot use command 
	
	~~~linux command
	cd /home/wwwroot && chown -R www wordpress/ && chgrp -R www wordpress/ 
	~~~
	
	to change the permission of wordpress folder, showing error 
	
	~~~linux command
	chown: cannot access 'wordpress/': No such file or directory
	~~~
	
	###### 	Solution: Use command 
	
	~~~linux command
	mv /home/wwwroot/default /home/wwwroot/wordpress
	~~~
	
	######  which can move wordpress folder to the correct path (the prerequisite is that you have already change nginx configuration by vim)
	
	​	-Cannot use command 
	
	~~~linux command
	cd /home/wwwroot && chown -R www wordpress/ && chgrp -R www wordpress/
	~~~
	
	to change the permission of wordpress folder, showing error 
	
	~~~linux command
	chown: changing ownership of 'wordpress/.user.ini': Operation not permitted
	~~~
	
	###### 	Solution: Use command 
	
	~~~linux command
	lsattr /home/wwwroot/wordpress/.user.ini
	~~~
	
	######  to check whether the current permission is -----i-----e-------.
	
	###### If there is "i" in the current permission state, use command 
	
	~~~linux command
	sudo chattr-i /home/wwwroot/wordpress/.user.ini
	~~~
	
	###### then try command
	
	~~~linux command
	cd /home/wwwroot && chown -R www wordpress/ && chgrp -R www wordpress/
	~~~
	
	###### again
	
2. #### Successfully set up WordPress

