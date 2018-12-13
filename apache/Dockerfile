FROM httpd:2.4

COPY ./certs/ /etc/ssl
COPY httpd.conf /usr/local/apache2/conf/httpd.conf
COPY httpd-ssl.conf /usr/local/apache2/conf/extra/httpd-ssl.conf
COPY teamleader.localhost.conf /usr/local/apache2/conf/teamleader.localhost.conf
