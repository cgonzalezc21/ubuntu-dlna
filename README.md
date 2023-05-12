# ubuntu-dlna

Este repositorio muestra como montar un servicio multimedia de DLNA usando minidlna.

# Implementación

1. Clona el repositorio

```bash
git clone https://github.com/cgonzalezc21/ubuntu-dlna.git
```

2. Modifica y crea la imagen del directorio `dlna-image` (opcional). Puedes usar la del docker-hub `carlosgc21/ubuntu-dlna:v1`.
En este caso, puedes pasar al siguiente paso. 

```bash
sudo docker build -t local:dlna .
```

3. Añade los videos en el directorio `media`

4. Levanta el contenedor

```bash
sudo docker-compose up -d
```

5. Disfruta del contenido desde tu cliente DLNA favorito
