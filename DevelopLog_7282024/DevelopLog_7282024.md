Recording Date: 7/28/2024

1. Struggling setting up WordPress(Really a lot of chanllenges)
	Challenges:
		-Cannot Enter the Password when logging in  MySQL
		Solution: the password entered is invisible but you did enter the password already, just make sure you the password you entered is correct and press "Enter". If you successfully log in, it would inform you a successful message.
		-Cannot change nginx configuration via vim
		Solution: use \q to exit MySQL, you cannot find nginx configuration when you arre in the MySQL.
		-Cannot access my web by using Public Internet Protocol Address(Public IP)
		Solution: Add 80 port(for http) and 443 port(for https) in the Security Group of Alibaba Cloud Console
		-Cannot use command "cd /home/wwwroot && chown -R www wordpress/ && chgrp -R www wordpress/" to change the permission of wordpress folder, showing error "chown: cannot access 'wordpress/': No such file or directory"
		Solution: Use command "mv /home/wwwroot/default /home/wwwroot/wordpress", which can move wordpress folder to the correct path (the prerequisite is that you have already change nginx configuration by vim)
		-Cannot use command "cd /home/wwwroot && chown -R www wordpress/ && chgrp -R www wordpress/" to change the permission of wordpress folder, showing error "chown: changing ownership of 'wordpress/.user.ini': Operation not permitted"
		Solution: Use command "lsattr /home/wwwroot/wordpress/.user.ini" to check whether the current permission is -----i-----e-------, if there is "i" in the current permission state, use command"sudo chattr-i /home/wwwroot/wordpress/.user.ini", then try command "cd /home/wwwroot && chown -R www wordpress/ && chgrp -R www wordpress/" again


