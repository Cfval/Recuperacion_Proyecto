<VirtualHost *:80>
    ServerAdmin carlosfrances.alu@gmail.com
    ServerName filmscfv.api.gleeze.com
    DocumentRoot /var/www/html/app

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined

    <Directory "/var/www/html/app">
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>

    #---- Configuración CORS -----
    RewriteEngine On
    RewriteCond %{REQUEST_METHOD} OPTIONS
    RewriteRule ^(.*)$ $1 [R=200]

    Header always add Access-Control-Allow-Origin "*"
    Header always add Access-Control-Allow-Methods "GET, POST, PUT, DELETE, OPTIONS"
    Header always add Access-Control-Allow-Headers "origin, x-requested-with, content-type"
</VirtualHost>
