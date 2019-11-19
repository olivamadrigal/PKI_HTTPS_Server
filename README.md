CREATE LOCAL PUBLIC KEY INFRASTRUCTURE
RUN APACHE LOCAL SERVER
CREATE CERTIFICATE & CORRESPONDING PRIVATE KEY FOR LOCAL WEBSITE
ACCESS: https://localhost



# PKI_HTTPS_Server
Design a PKI, HTTPS server, and run website with certificate.

PKI = public key infrastructure is used by PKC (public key cryptography) cryptosystems. 
It is used to sign public keys using a trusted third party (CA = Certificate Authority).


Please follow the tutorial here to create your own custom CA. 
https://pki-tutorial.readthedocs.io/en/latest/simple/

May also generate certificate and using similar openssl crypto libary commands, without having
to specify domain component (.com, .org, etc)

Install APACHE on your machine or if on MAC is already there. Follow this tutorial
get know which modules to unload for basic functionality:
https://coolestguidesontheplanet.com/install-apache-mysql-php-on-macos-mojave-10-14/

# MODIFY:
httdp.conf: 
For SSL you must uncomment: 
LoadModule ssl_module modules/mod_ssl.so
LoadModule socache_shmcb_module libexec/apache2/mod_socache_shmcb.so
Include conf/extra/httpd-ssl.conf
	
httpd-ssl.conf
ServerName localhost:443
SSLCertificateFile "private/etc//apache/apache2/localhost.cert"
SSLCertificateKeyFile "private/etc//apache2/localhost.key"

TRY to access: https://localhost

build testing webstite, index.html using HTML5 skeleton:
https://www.w3schools.com/html/html5_intro.asp

place inside documentroot


