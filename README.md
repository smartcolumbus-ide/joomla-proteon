### Installation and Deloyment of Joomla

Download the VestaCP for system monitoring as a sudo / root user

	sudo curl -O http://vestacp.com/pub/vst-install.sh
	
Install the downloaded files

	sudo bash vst-install.sh
	
The installation will install required resources, press 'Y' when promted. You will also be promted to provide an email address and hostname for the Vesta Panel. Example panel.myexample.com/pub/vst-install. This process takes approximately 5 minutes to complete.

Port 8083 needs to be open to traffic to be able to view the panel. This port should be restricted to the IP address of developer users. Do not open this port to all traffic.

(Can this be done via CLI?)
Login with the credential provided via email and complete the following task
1. Add a new Web URL for Vesta by entering a domain, and uncheck DNA and Mail support. Add FTP account to allow for file transfers.

Installation of Joomla

	sudo chown -R centos:centos /home/admin
	
Transfer Files (this should be part of the clone)	
Files to Copy - sandbox.zip
Path to Copy To - /home/centos/web/<site>/public_html

	rm index.html
	rm robots.txt
	unzip sandbox.zip
	
	sudo chown -R admin:admin /home/admin
		
Deploying the site template via the Joomla GUI.
This repostitory contains the template used for the Smart Columbus SCOS site. The current method of deployment of the (not CI) takes a backup of the modified template and then restores from the backup. In future iterations, the template will be sourced so that changes can be reflected in a CI environment.

Navigate to the <site_url>/installation/index.php > Next
Enter the Databse Type (MySQLi)
Database Server Host Name 
UN / PW and Database Name

Click Next to Restore Backup

