FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

# Instalación de paquetes base
RUN apt update && apt install -y minidlna

# Se copia el archivo de configuración para el servidor DLNA
COPY ./cfg/minidlna.conf /etc/minidlna.conf  

# Se configura el usuario
RUN useradd -m mini

# Se crea el directorio para almacenar los registros y la ejecución del servicio
RUN mkdir /var/log/minidlna && mkdir /run/minidlna && chown minidlna:minidlna /run/minidlna

# Se copia el archivo de inicio
COPY ./cfg/startup.sh /root/

# Se expone el puerto, aunque no es completamente necesario
EXPOSE 8200:8200/tcp
EXPOSE 239.255.255.250:1900:1900/udp

# Se configura y ejecuta el archivo al iniciar la imagen
RUN chmod u+x /root/startup.sh
CMD ["/bin/bash", "-c", "/root/startup.sh"]

