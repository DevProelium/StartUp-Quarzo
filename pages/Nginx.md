-
- # Nginx
- ## Descripción
  Nginx es un servidor web de alto rendimiento, también conocido por su capacidad para actuar como proxy inverso, balanceador de carga y caché HTTP. Es conocido por su alta concurrencia, bajo consumo de memoria y su arquitectura asincrónica.
- ## Instalación en Ubuntu 24.04
- ### Paso 1: Actualizar el sistema
  Antes de instalar cualquier paquete nuevo, es una buena práctica actualizar la lista de paquetes disponibles y sus versiones.  
  
  ```bash  
  sudo apt update  
  sudo apt upgrade  
  - Paso 2: Instalar Nginx
  Para instalar Nginx, ejecuta el siguiente comando:
  - sudo apt install nginx
  Paso 3: Iniciar y habilitar Nginx  
  Una vez instalado, inicia el servicio Nginx y habilítalo para que se inicie automáticamente al arrancar el sistema.  
  - sudo systemctl start nginx
  sudo systemctl enable nginx  
  Paso 4: Verificar el estado de Nginx  
  Para asegurarte de que Nginx se está ejecutando correctamente, verifica su estado:  
  - sudo systemctl status nginx
  Paso 5: Configurar el firewall  
  Si tienes un firewall habilitado, asegúrate de permitir el tráfico HTTP y HTTPS.  
  - sudo ufw allow 'Nginx Full'
  Comandos Útiles de Nginx  
  Comando	Descripción  
  sudo systemctl start nginx	Inicia el servicio Nginx.  
  sudo systemctl stop nginx	Detiene el servicio Nginx.  
  sudo systemctl restart nginx	Reinicia el servicio Nginx.  
  sudo systemctl reload nginx	Recarga la configuración de Nginx sin detener el servicio.  
  sudo systemctl enable nginx	Habilita Nginx para que se inicie automáticamente al arrancar el sistema.  
  sudo systemctl disable nginx	Deshabilita Nginx para que no se inicie automáticamente al arrancar el sistema.  
  sudo systemctl status nginx	Muestra el estado del servicio Nginx.  
  sudo nginx -t	Prueba la configuración de Nginx para detectar errores de sintaxis.  
  sudo tail -f /var/log/nginx/error.log	Muestra los últimos registros de errores de Nginx en tiempo real.  
  sudo tail -f /var/log/nginx/access.log	Muestra los últimos registros de acceso de Nginx en tiempo real.  
  Configuración Básica de Nginx  
  Archivos de Configuración  
  Los archivos de configuración de Nginx se encuentran en el directorio /etc/nginx. Los archivos más importantes son:  
  - /etc/nginx/nginx.conf: Archivo de configuración principal.
  /etc/nginx/sites-available/: Directorios donde se almacenan los archivos de configuración de los sitios web disponibles.  
  /etc/nginx/sites-enabled/: Directorios donde se almacenan los enlaces simbólicos a los archivos de configuración de los sitios web habilitados.  
  - Crear un Nuevo Sitio Web
  Para crear un nuevo sitio web, sigue estos pasos:  
  - Crea un nuevo archivo de configuración en /etc/nginx/sites-available/:
  
  sudo nano /etc/nginx/sites-available/mi_sitio  
  Añade la siguiente configuración básica:  
  
  server {  
    listen 80;  
    server_name mi_sitio.com www.mi_sitio.com;  
  - root /var/www/mi_sitio;
    index index.html index.htm;  
  - location / {
        try_files $uri $uri/ =404;  
    }  
  }  
  Crea un enlace simbólico en /etc/nginx/sites-enabled/ para habilitar el sitio:  
  
  sudo ln -s /etc/nginx/sites-available/mi_sitio /etc/nginx/sites-enabled/  
  Prueba la configuración para detectar errores de sintaxis:  
  
  sudo nginx -t  
  Recarga la configuración de Nginx:  
  
  sudo systemctl reload nginx  
  -
  - Página Dedicada
  Para más información sobre Nginx, puedes visitar la página oficial de Nginx.
  
  GPT-4o mini:
  Aquí tienes el contenido transformado a formato Markdown para tu Logseq:
  
  ```markdown
- # Nginx
- ## Descripción
  Nginx es un servidor web de alto rendimiento, también conocido por su capacidad para actuar como proxy inverso, balanceador de carga y caché HTTP. Es conocido por su alta concurrencia, bajo consumo de memoria y su arquitectura asincrónica.
- ## Instalación en Ubuntu 24.04
- ### Paso 1: Actualizar el sistema
  Antes de instalar cualquier paquete nuevo, es una buena práctica actualizar la lista de paquetes disponibles y sus versiones.
  
  ```bash
  sudo apt update  
  sudo apt upgrade  
  ```
- ### Paso 2: Instalar Nginx
  Para instalar Nginx, ejecuta el siguiente comando:
  
  ```bash
  sudo apt install nginx
  ```
- ### Paso 3: Iniciar y habilitar Nginx  
  Una vez instalado, inicia el servicio Nginx y habilítalo para que se inicie automáticamente al arrancar el sistema.
  
  ```bash
  sudo systemctl start nginx  
  sudo systemctl enable nginx  
  ```
- ### Paso 4: Verificar el estado de Nginx  
  Para asegurarte de que Nginx se está ejecutando correctamente, verifica su estado:
  
  ```bash
  sudo systemctl status nginx  
  ```
- ### Paso 5: Configurar el firewall  
  Si tienes un firewall habilitado, asegúrate de permitir el tráfico HTTP y HTTPS.
  
  ```bash
  sudo ufw allow 'Nginx Full'  
  ```
- ## Comandos Útiles de Nginx  
  | Comando | Descripción |
  |---------|-------------|
  | `sudo systemctl start nginx` | Inicia el servicio Nginx. |
  | `sudo systemctl stop nginx` | Detiene el servicio Nginx. |
  | `sudo systemctl restart nginx` | Reinicia el servicio Nginx. |
  | `sudo systemctl reload nginx` | Recarga la configuración de Nginx sin detener el servicio. |
  | `sudo systemctl enable nginx` | Habilita Nginx para que se inicie automáticamente al arrancar el sistema. |
  | `sudo systemctl disable nginx` | Deshabilita Nginx para que no se inicie automáticamente al arrancar el sistema. |
  | `sudo systemctl status nginx` | Muestra el estado del servicio Nginx. |
  | `sudo nginx -t` | Prueba la configuración de Nginx para detectar errores de sintaxis. |
  | `sudo tail -f /var/log/nginx/error.log` | Muestra los últimos registros de errores de Nginx en tiempo real. |
  | `sudo tail -f /var/log/nginx/access.log` | Muestra los últimos registros de acceso de Nginx en tiempo real. |
- ## Configuración Básica de Nginx
- ### Archivos de Configuración  
  Los archivos de configuración de Nginx se encuentran en el directorio `/etc/nginx`. Los archivos más importantes son:
- `/etc/nginx/nginx.conf`: Archivo de configuración principal.
- `/etc/nginx/sites-available/`: Directorios donde se almacenan los archivos de configuración de los sitios web disponibles.
- `/etc/nginx/sites-enabled/`: Directorios donde se almacenan los enlaces simbólicos a los archivos de configuración de los sitios web habilitados.
- ### Crear un Nuevo Sitio Web  
  Para crear un nuevo sitio web, sigue estos pasos:  
  1. Crea un nuevo archivo de configuración en `/etc/nginx/sites-available/`:
  
    ```bash
    sudo nano /etc/nginx/sites-available/mi_sitio  
    ```
  
  2. Añade la siguiente configuración básica:  
  
    ```nginx
    server {  
        listen 80;  
        server_name mi_sitio.com www.mi_sitio.com;  
        root /var/www/mi_sitio;  
        index index.html index.htm;  
  
        location / {
            try_files $uri $uri/ =404;  
        }  
    }  
    ```
  
  3. Crea un enlace simbólico en `/etc/nginx/sites-enabled/` para habilitar el sitio:  
  
    ```bash
    sudo ln -s /etc/nginx/sites-available/mi_sitio /etc/nginx/sites-enabled/  
    ```
  
  4. Prueba la configuración para detectar errores de sintaxis:  
  
    ```bash
    sudo nginx -t  
    ```
  
  5. Recarga la configuración de Nginx:  
  
    ```bash
    sudo systemctl reload nginx  
    ```
- ## Página Dedicada  
  Para más información sobre Nginx, puedes visitar la página oficial de Nginx.
  ```
- []