# LAMP-Apache2-conf


                 
<VirtualHost *:80>
    ServerName kochi.dev
    ServerAlias www.kochi.dev
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/html
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
RewriteEngine on
RewriteCond %{SERVER_NAME} =kochi.dev [OR]
RewriteCond %{SERVER_NAME} =www.kochi.dev
RewriteRule ^ https://%{SERVER_NAME}%{REQUEST_URI} [END,NE,R=permanent]
</VirtualHost>



