# USBIP

Configuración usada para compartir escaner desde openwrt (sirve para cualquier dispositivo usb), se verá como dispositivo local en el ordenador cliente.

## Server (OpenWRT en este caso)

### Install

  ```opkg update```

  ```opkg install kmod-usb-core kmod-usb2 usbip-server usbip-client usbutils```

### Config

  - Obten el usb, en mi caso '1-1.4'

    ```usbip list -l```

  - Añadir ésta linea al /etc/rc.local o al /etc/init.d/usbipd

    ```usbip bind -b 1-1.4``` 

  - Reiniciar
    
    ``` reboot ``` 


## Client

### Install

  ``` sudo apt install usbip ``` 

### Config

  - Cargar modulo necesario
  
    ```sudo modprobe vhci-hcd``` 

  - Para añadirlo hay que ejecutar este comando, cambiando la ip y el id del usb si es necesario
  
    ```usbip attach -r 192.168.1.3 -b 1-1.4 ``` 

### Persistencia
  - Para hacerlo persistente puedes añadir ésta linea al /etc/rc.local
  
  - Cargar modulo necesario al iniciar

    ``` echo vhci-hcd | sudo tee /etc/modules-load.d/vhci-hcd.conf ``` 

