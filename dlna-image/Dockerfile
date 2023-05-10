FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

# Instalación de paquetes base
RUN apt update && apt install -y minidlna supervisor

# Se copia el archivo de configuración para el servidor DLNA
COPY ./cfg/minidlna.conf /etc/minidlna.conf  

# Se copia el archivo de configruación de supervisor para iniciar el servicio
COPY ./cfg/supervisor.conf /etc/supervisor/conf.d/

# Se copia el archivo de inicio
COPY ./cfg/startup.sh /root/

# Se expone el puerto
EXPOSE 8200

# Se xonfigura y ejecuta el archivo al iniciar la imagen
RUN chmod u+x /root/startup.sh
CMD ["/bin/bash", "-c", "/root/startup.sh"]
