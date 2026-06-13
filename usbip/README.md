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

### Config
