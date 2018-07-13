show ciphers
#openssl ciphers -v | awk '{print $2}' | sort | uniq

create certificate with openssl (reference link https://www.shellhacks.com/create-csr-openssl-without-prompt-non-interactive/)
#openssl req -nodes -newkey rsa:2048 -keyout /opt/cert/example.key -out /opt/cert/example.csr -subj "/C=GB/ST=Athlone/L=Athlone/O=Global Security/OU=IT Department/CN=example.com"

SSL Protocol
https://serverfault.com/questions/314858/how-to-enable-tls-1-1-and-1-2-with-openssl-and-apache

just support TLSv1.2
SSLProtocol -all +TLSv1.2
-all is removing other ssl protocol (SSL 1,2,3 TLS1)

just support SSLv2
SSLProtocol -all SSLv2

try openssl client connect
openssl s_client -connect localhost:443 -ssl3

dockerfile reference
https://github.com/MarvAmBass/docker-apache2-ssl-secure

SSL vs. TLS - What's the Difference?
https://www.globalsign.com/en/blog/ssl-vs-tls-difference/

apt-get install nmap
nmap --script ssl-enum-ciphers -p 443 localhost

java -jar certificate-test-jar-with-dependencies 192.168.99.100 443
