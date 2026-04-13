# CONCEPTOS Y COMANDOS
+ Concepto: ¿Qué es un contenedor vs una Máquina Virtual?  
+ Arquitectura: El motor de Docker (Daemon), Imágenes y Contenedores.  
+ Ciclo de vida: run, stop, ps, rm, logs.  
+ Networking básico: Mapeo de puertos (-p host:container).  

+ Docker soluciona esto creando "habitaciones estancas" (contenedores). Cada aplicación lleva su propio sistema operativo mínimo, sus librerías y su configuración. Si el contenedor se rompe, lo borras y levantas otro igual en milisegundos.

**1. INSTALACIÓN DEL MOTOR *DOCKER ENGINE***
```
# Actualizamos el índice de paquetes
sudo apt-get update

# Instalamos paquetes necesarios
sudo apt-get install -y ca-certificates curl gnupg

# Añadimos la clave GPG oficial de Docker
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

# Configuramos el repositorio
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Instalamos Docker
sudo apt-get update
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

**2. PERMISOS COMANDOS DOCKER**  
Para no tener que escribir sudo en cada comando de Docker, añade tu usuario al grupo docker:
```
sudo usermod -aG docker $USER
```
> IMPORTANTE: Para que esto surta efecto, tienes que salir de la sesión (exit) y volver a entrar por SSH.

**3. PRIMER EJEMPLO DOCKER**
```
docker run -d -p 8081:80 --name mi-web-container nginx
```  
> run: Crea y arranca un contenedor.  
> -d (detached): Lo corre en segundo plano (para que no te bloquee la terminal).  
> -p 8081:80: Mapeo de puertos. El puerto 8081 de tu servidor conectará con el 80 interno del contenedor.  
> --name: Le ponemos un nombre para no tener que usar IDs largos.  
>  nginx: La imagen (el molde) que queremos usar.  

**4. Resultados:**
```
vagrant@ubuntu-focal:~$ docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS              PORTS                                     NAMES
4a1fde554d2a   nginx     "/docker-entrypoint.…"   About a minute ago   Up About a minute   0.0.0.0:8081->80/tcp, [::]:8081->80/tcp   mi-web-container

vagrant@ubuntu-focal:~$ ss  -tunlp | grep 8081
tcp   LISTEN 0       4096              0.0.0.0:8081        0.0.0.0:*            
tcp   LISTEN 0       4096                 [::]:8081           [::]:*         

vagrant@ubuntu-focal:~$ curl -I http://localhost:8081
HTTP/1.1 200 OK
Server: nginx/1.29.8
Date: Mon, 13 Apr 2026 15:06:34 GMT
Content-Type: text/html
Content-Length: 896
Last-Modified: Tue, 07 Apr 2026 11:37:12 GMT
Connection: keep-alive
ETag: "69d4ec68-380"
Accept-Ranges: bytes
```

**5. COMANDOS BÁSICOS**
+ Parar y Arrancar (Sin destruir):
```
docker stop mi-web-container
# Ahora haz un docker ps (verás que desaparece)
# Haz un docker ps -a (verás que sigue ahí pero en estado 'Exited')

docker start mi-web-container
# Haz un docker ps (vuelve a estar vivo)
```

+ Ver los logs:
```
docker logs -f mi-web-container
```

+ Entrar al contenedor:
```
docker exec -it mi-web-container bash
```
> -it: Interactivo + Terminal.  
> bash: El programa que quieres ejecutar dentro.  

+ Parar y borrar un contenedor:
```
docker stop mi-web-container
docker rm mi-web-container
```
> docker stop: Apaga el motor pero mantiene la "caja" y lo que hayas escrito dentro.  
> docker rm: Tritura la "caja". Si no habías guardado los datos en un volumen (lo veremos en el Bloque 2), esos datos se pierden para siempre.  