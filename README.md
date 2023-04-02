# Opening a Port for Other Devices to Access Your Project
To allow other devices to access your project, you need to open another port on your device. Follow the steps below to do so:
# Steps to Follow:
Step 1: Install `XAMPP` on your device and open it.

Step 2: Open the `httpd.conf` file located at `path\to\xampp\apache\conf\httpd.conf`.

Step 3: Find the line `Listen 80` and add `Listen 8080` to the line below it.

Step 4: Find the line ServerName `localhost:80` and add ServerName `localhost:8080` to the line below it.

Step 5: Find the following content in the file:
```
<Directory "path/to/xampp/htdocs">
    ...
</Directory>
```
and add the following content above it:
```
<VirtualHost *:[PORT]>
   DocumentRoot "path/to/xampp/htdocs/<project name>"
   ServerName localhost:[PORT]
   <Directory "path/to/xampp/htdocs/<project name>">
       AllowOverride All
       Require all granted
   </Directory>
</VirtualHost>
```
Make sure to replace `[PORT]` with the port number you opened in step 3, `<project name>` with the name of your project, and `path/to/xampp/htdocs/<project name>` with the path to your project.

Step 6: Save the file and restart Apache in XAMPP.

Step 7: Open the Command Prompt and type ipconfig to get your IPv4 address.

Step 8: Open your browser and type `http://[IPv4 address]:[PORT]/<project name>` to access your project.

## Good luck!