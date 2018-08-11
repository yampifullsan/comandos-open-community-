# comandos-open-community


* Cambiar el nombre de host a myhost.opencommunity.org 

     #hostnamectl set-hostname myhostacecinxs.opencommunity.org

* Configure su nombre de host, dirección IP, puerta de enlace y DNS.

     #nmcli connection down eth0

     #nmcli connection modify eth0 ipv4.addresses 172.24.40.41/24 ipv4.gateway 172.24.40.1 ipv4.dns 172.24.40.1
     
     #nmcli connection up eth0
     
     
* Descargue una Imagen (imagen.iso) y móntelo automáticamente bajo /media/cdrom y que surten efecto automáticamente en el arranque-inicio. 

     Se agrega el iso como device CDROM a la máquina virtual
     
     En este caso, la carpeta en la que vamos a montar se llama "iso"
     
     #mkdir /mnt/iso
     
     #echo "/dev/sr0 /mnt/iso iso9660 ro,nosuid,nodev,relatime 0 0" > /etc/fstab
     
     #cat /mnt/iso/media.repo >> /etc/yum.repos.d/local.repo
    
* Descarge una Imagen (imagen.iso) y móntelo automáticamente bajo /media/cdrom y que surten efecto automáticamente en el arranque-inicio.
     En el virtualizador agregamos la imagen iso (en una maquina fisica seria el equivalente a instroducir el disco de la iso en el reproductor dvd)
     Creamos directorio 
     #mkdir /mnt/iso
     
     Verificamos que la imagen iso se haya montado.
     #mount
     Observamos las características desplegadas después del comando “mount” para el siguiente comando.   
     #echo “dev/sr0 /mnt/iso iso9660 ro,nosuid,nodev,relatime 0 0” >> /etc/fstab
     #umount /run/media/root/RHEL-7.3\ Server.x86_64/
     #df -h
     #mount -a
     #df -h
     
     Creamos el repositorio.
     #cat /mnt/iso/media.repo >> /etc/yum.repos.d/base.repo

       Modificar el archivo:
        #vi /etc/yum.repos.d/base.repo 
        Agregar después de mediaid las siguientes dos lineas:
        baseurl=file:///mnt/iso
        enabled=1

