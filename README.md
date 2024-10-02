sudo apt update && sudo apt install -y nginx: Updates the package list on the system and installs the nginx web server.

sudo apt update && sudo apt install certbot python3-certbot-nginx: Updates the package list on the system and installs Certbot, a tool for obtaining SSL certificates from Let's Encrypt, and the Certbot plugin for nginx.

sudo mkdir -p /var/www/ganeshdevops.site/html: Creates a directory structure to host the website files for the domain ganeshdevops.site.

sudo chown -R $USER:$USER /var/www/ganeshdevops.site/html: Changes the ownership of the directory to the current user.

sudo chmod -R 755 /var/www/ganeshdevops.site: Changes the permissions of the directory to allow read, write, and execute access for the owner and read and execute access for others.

nano /var/www/ganeshdevops.site/html/index.html: Opens a text editor (nano) to create/edit the HTML file for the website homepage. You will paste the provided HTML code into this file.

sudo nano /etc/nginx/sites-available/ganeshdevops.site: Opens a text editor to create/edit a server block configuration file for nginx for the domain ganeshdevops.site. You will paste the provided nginx configuration into this file.

sudo ln -s /etc/nginx/sites-available/ganeshdevops.site /etc/nginx/sites-enabled/: Creates a symbolic link from the server block configuration file in sites-available to sites-enabled, enabling the configuration for nginx to use.

sudo nginx -t: Tests the nginx configuration for any syntax errors.

sudo systemctl restart nginx: Restarts the nginx service to apply the new configuration changes.

sudo certbot certonly --agree-tos --email tirumaniganesh007@gmail.com --manual --preferred-challenges=dns -d .ganeshdevops.site --server https://acme-v02.api.letsencrypt.org/directory: Uses Certbot to obtain a SSL certificate from Let's Encrypt for the domain ganeshdevops.site and any subdomains (.ganeshdevops.site) using DNS verification.

After running these commands, you'll have a basic web server setup with nginx and a valid SSL certificate installed for the domain ganeshdevops.site.
