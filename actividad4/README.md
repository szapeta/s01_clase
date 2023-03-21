se crea el archivo .sh que incluye el código para imprimir la bienvenida y mostrar la fecha y hora

```

#!/bin/bash
# Sergio Mynor David Felipe Zapeta
# SO1

echo Bienvenido a la revision de la actividad 4

now="$(date)"
now="$(date +'%d/%m/%Y')"
printf "Hoy es: %s\n" "$now"

```

Luego debemos de crear un servicio  llamado servicio_practica4.service en el directorio /lib/systemd/system que ejecutara el archivo .sh

```
[Unit]
Description=Servicio creado para la practica 4
After=network.target
 
[Service]
User=root
WorkingDirectory=/ruta/del/archivo
Type=simple
ExecStart=/ruta/del/archivo
GuessMainPID=no
 
[Install]
WantedBy=multi-user.target

```

Luego debemos de activar el servicio para ejecutar el archivo .sh

Ejecutaremos los siguientes comandos

```
//Habilitar el inicio automatico del servicio
sudo systemctl daemon-reload

sudo systemctl enable servicio_practica4.service

//comando para iniciar el servicio
sudo systemctl start servicio_practica4.service

//comando para detener el servicio
sudo systemctl stop servicio_practica4.service

//comando para ver el estado del servicio
sudo systemctl status servicio_practica4.service
```