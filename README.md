# comandos-open-community


* Cambiar el nombre de host a myhost.opencommunity.org 

     #hostnamectl set-hostname myhostacecinxs.opencommunity.org

* Configure su nombre de host, dirección IP, puerta de enlace y DNS.

     #nmcli connection down eth0

     #nmcli connection modify eth0 ipv4.addresses 172.24.40.41/24 ipv4.gateway 172.24.40.1 ipv4.dns 172.24.40.1
     
     #nmcli connection up eth0
