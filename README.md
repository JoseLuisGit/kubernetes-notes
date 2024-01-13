# Kubernetes

Kubernetes es un sistema de código abierto para la automatización del despliegue, ajuste de escala y manejo de aplicaciones en contenedores que fue originalmente diseñado por Google y donado a la Cloud Native Computing Foundation. Soporta diferentes entornos para la ejecución de contenedores, incluyendo Docker.

## Que son los containers?

Los contenedores son un tipo de virtualización a nivel de sistema operativo que permite ejecutar aplicaciones y sus dependencias de forma aislada. Los contenedores son más livianos que las máquinas virtuales, ya que no necesitan un sistema operativo por cada aplicación, sino que comparten el mismo sistema operativo entre todos los contenedores. Esto permite que los contenedores sean más portables y eficientes que las máquinas virtuales.

## Que es la virtualización?

Es un proceso de abstraccion donde pemite compartir los recursos del hardware de una simple instancia a multiples instancias virtuales de un sistema operativo.

### Maquinas Virtuales

Son un software que emula un sistema de computo y puede ejecutar programas como si fuese una computadora real. Este software se ejecuta sobre un sistema operativo base y a su vez puede ejecutar otros sistemas operativos invitados.

#### Problemas de las Maquinas Virtuales

* Tamaño de las maquinas virtuales
* Tiempo de arranque
* Consumo de recursos

### Contenedores

La diferencia con una maquina virtual es que los contenedores no necesitan un sistema operativo invitado, sino que comparten el mismo sistema operativo entre todos los contenedores. Esto permite que los contenedores sean más portables y eficientes que las máquinas virtuales.

* Se tiene un solo proceso del host del sistema operativo
* Es mas liviano y es mas rapido al iniciar
* Es facil de administrar

Los contenedores es un concepto general que docker, docker es solo una plataforma que trabaja con contenedores.
Docker tiene unos competidores como LXD/LXC, Podman, Kaniko, Buildah, CRI-O, etc.

#### OCI (Open Container Initiative)

Es una organizacion que se encarga de estandarizar los contenedores, para que todos los contenedores sean compatibles entre si.

## Docker

Es una plataforma de software que permite crear, probar e implementar aplicaciones rápidamente. Docker empaqueta software en unidades estandarizadas llamadas contenedores que incluyen todo lo necesario para que el software se ejecute, incluidas bibliotecas, herramientas de sistema, código y tiempo de ejecución. Con Docker, puede implementar y ajustar la escala de aplicaciones rápidamente en cualquier entorno y saber que su código se ejecutará.

### Docker images

Es una plantilla de solo lectura con instrucciones para crear un contenedor Docker. A menudo, una imagen de Docker se basa en otra imagen, con algunas personalizaciones adicionales. Por ejemplo, puede construir una imagen que se base en la imagen predeterminada de Ubuntu, pero instale el servidor web Apache y su aplicación, así como los detalles de la configuración necesarios para que su aplicación se ejecute con el servidor web Apache.

#### Como se almacenar las imagenes?

* Las imagenes son archivos como cualquier otro.
* Las imagenes se almacenan en un registro de imagenes.
* Docker Hub es un registro de imagenes publico.
* Las imagenes publicas pueden ser usados por cualquiera para crear contenedores.
* Las imagenes publicas pueden ser extendidas con capas personalizadas.
* Las imagenes privadas requieren autenticacion para ser usadas.

### Instacion docker en ubuntu

```bash
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```



