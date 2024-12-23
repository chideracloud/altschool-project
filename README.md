# altschool exam project
DEPLOYING THE HTML PAGE ON MY AWS EC2 UBUNTU SERVER
http://18.206.175.218

started my logging into my AWS console,then navigated to EC2 instances ;
began creating a new ec2 instance,configuring it to be my ubuntu server by clicking on Ubuntu AMI images,configured the network settings,the VPC and subnets to make it hihly available and also by allowing port 80 HTTP,HTTPS,SSH on the instance;
created my secure key pair,then successfully created the instance;
Afterwards,i connected into the server,as shown in the screenshots,i ran the sudo apt update command to update the server;
then ran the sudo apt install nginx -y to install nginx as my web server;
proceeded to run nginx -v to check if it successfully installed and the version installed,the nginx version was 1.24.0;

then i proceeded to create a simple HTML page using VScode with the necessary details as instructed;
i filled out my name and every required detail;
then i saved the html file as an index.html file on my local machine;
using the scp command as shown in the screenshot to move the index.html file from my local computer to my remote ubuntu server;
then i used 'sudo mv /home/ubuntu/index.html /var/www/html/' to move the index.html file to the default Nginx document root directory;
using the sudo chown command to verify the file has the right ownership,then sudo chmod to enforce the right permissions to the file;

'sudo nano /etc/nginx/sites-available/default' was used to make sure Nginx is configured to serve the /var/www/html/index.html in the root directory;
i thorouhgly ensured the file and parameters were correctly configured and pointing in the right direction;

ran the sudo 'nginx -t' to ensure the Nginx configuration is valid;
then i applied changes and reloaded Nginx using 'sudo systemctl reload nginx' command;

then i hit the public IP address of my EC2 ubuntu server instance which is http://18.206.175.218 and HTML page was correctly displayed;

