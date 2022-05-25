# Docker Microservicios

<!-- [TODO] agregar descripción --> 

## Nota

Este repositorio fue creado para corregir algunos errores que contenía el repositorio original donde
desarrollamos el proyecto. Este repositorio funciona correctamente.

[El repositorio original (contiene un error) se encuentra aqui](https://github.com/AsuJuve/Microservicios_Global-Surance-System)

## Estructura del proyecto

Este repositorio contiene los siguientes directorios y archivos:

```bash
    ├── cliente                              # componente GUI que funciona como cliente
    ├── gestor-de-clientes                   # microservicio gestor de clientes
    ├── docs                                 # carpeta de documentación
    │  ├── context-view.png                  # vista del contexto del sistema
    │  ├── global-assurance.drawio           # archivo editable de daiagramas del sistema 
    ├── notificador                          # microservicio notificador 
    ├── pagos                                # microservicio pagos
    ├── reporteador                          # microservicio reporteador
    ├── simulador                            # componente que simula los pagos realizados
    ├── tyk                                  # archivos compartidos con el gateway
    │  ├── apps                              # definición de APIs en el gateway
    │  |  ├── keyless-gestor-clientes.json   # definición de microservicio API
    │  |  ├── keyless-notificador.json       # definición de microservicio Notifier
    │  |  ├── keyless-pagos.json             # definición de microservicio Payment
    │  |  ├── keyless-reporteador.json       # definición de microservicio Reporter
    │  ├── tyk.standalone.conf               # archivo de configuración de tyk
    ├── .gitignore                           # exclusiones de git
    ├── docker-compose.yml                   # definición de contenedores para ambiente docker
    ├── README.md                            # este archivo
```

## Instalación

Descarga el código del repositorio utilizando el siguiente comando:

`git clone https://gitlab.com/tareas-arquitectura-de-software-curso/microservicios/docker-microservicios.git`

Ingresa a la carpeta del proyecto:

`cd docker-microservicios`

Descarga el código fuente de los microservicios y componentes del sistema:

`git submodule update --init --recursive`

## Configuración

Antes de arrancar el sistema deberás realizar las siguientes modificaciones en los archivos de configuración. 

> identifica la IP de tu máquina y reemplazala por el valor actual.

### Gestor de clientes

Para este microservicio no hay que realizar alguna configuración

### Cliente

Accede al archivo `cliente/.env` y actualiza el valor de la variable `GATEWAY_HOST`:

```bash
GATEWAY_HOST=tyk-gateway
```

### Notificador

Accede al archivo `notificador/settings.ini` y actualiza las variables `TOKEN` y `CHAT_ID`:

```bash
TOKEN = <TELEGRAM_TOKEN>
CHAT_ID = <TELEGRAM_CHAT_ID>
```

> puedes consultar el siguiente [enlace](https://medium.com/@goyoregalado/bots-de-telegram-en-python-134b964fcdf7) 
> para conocer más acerca del `TOKEN` y `CHAT_ID` de telegram.

### Pagos

Para este microservicio no hay que realizar alguna configuración

### Reporteador

Para este microservicio no hay que realizar alguna configuración

### Gateway

Para este componente no hay que realizar alguna configuración

## Ejecución

Para ejecutar el sistema utiliza el siguiente comando:

`docker-compose up -d`

Para detener el sistema utiliza el siguiente comando:

`docker-compose down`

> al ejecutar el sistema se creará una carpeta `volume` donde se guardará la información que se genere en el sistema
> si deseas reiniciar los datos basta con eliminar dicha carpeta

## Diagramas

![alt text][diagrama1]
[diagrama1]: https://github.com/Khelthal/docker-microservicios/blob/main/docs/Vista%20din%C3%A1mica%20del%20requerimiento%20de%20usuario%20a)%20.drawio.png?raw=true "Diagrama 1"

### Vista dinámica de obtención de pagos.

![alt text][diagrama2]
[diagrama2]: https://github.com/Khelthal/docker-microservicios/blob/main/docs/Vista%20dinamica%20R2.png?raw=true "Diagrama 2"

### Vista dinámica de envío de notificaciones.

![alt text][diagrama3]
[diagrama3]: https://github.com/Khelthal/docker-microservicios/blob/main/docs/Envio%20poliza%20diagrama.png?raw=true "Diagrama 3"

### Vista dinámica de env

## Preguntas Frecuentes

### ¿Necesito instalar Docker?

Por supuesto, la herramienta Docker es vital para la ejecución de este sistema. Para conocer más acerca de Docker puedes visitar el siguiente [enlace](https://medium.com/@javiervivanco/que-es-docker-79d506f7b2fc).

> Para realizar la instalación de Docker en Windows puedes consultar el siguiente [enlace](https://medium.com/@tushar0618/installing-docker-desktop-on-window-10-501e594fc5eb)


> Para realizar la instalación de Docker en Linux puedes consultar el siguiente [enlace](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04-es)

## Versión

3.0.0 - Febrero 2022

## Autores

- Perla Velasco
- Yonathan Martinez
- Jorge Solis
- Elías Emiliano Beltrán González
- Román Guzmán Valles
- Juventino Aguilar Correa
- Jorge Luis Díaz Serda
