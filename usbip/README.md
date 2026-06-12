# USBIP

Configuración usada para compartir escaner desde openwrt (sirve para cualquier dispositivo usb), se verá como dispositivo local en el ordenador cliente.

## Server (OpenWRT en este caso)

### Install

  ```opkg update```
  ```opkg install kmod-usb-core kmod-usb2 usbip-server usbip-client usbutils```


### Config

  ```usbip list -l```bash

  Debe devolver un valor tipo '1-1.4',edita el script y cambia el valor en esta variable

## Client

### Install

### Config
