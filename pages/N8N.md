# n8n
- ## Descripción
  n8n es una herramienta de automatización de flujo de trabajo de código abierto que te permite conectar diferentes aplicaciones y servicios para automatizar tareas repetitivas. Es similar a Zapier o Integromat, pero con la ventaja de ser autoalojable y altamente personalizable.
- ## Instalación en Ubuntu 24.04
- ### Paso 1: Actualizar el sistema
  Antes de instalar cualquier paquete nuevo, es una buena práctica actualizar la lista de paquetes disponibles y sus versiones.
  
  ```bash
  sudo apt update
  sudo apt upgrade
  ```
- ### Paso 2: Instalar dependencias
  n8n requiere Node.js y npm para su ejecución. Instala Node.js y npm utilizando los siguientes comandos:
  
  ```bash
  sudo apt install -y nodejs npm
  ```
- ### Paso 3: Instalar n8n
  Puedes instalar n8n utilizando npm. Ejecuta el siguiente comando para instalar n8n globalmente:
  
  ```bash
  sudo npm install n8n -g
  ```
- ### Paso 4: Iniciar n8n
  Una vez instalado, puedes iniciar n8n utilizando el siguiente comando:
  
  ```bash
  n8n
  ```
  
  Para ejecutar n8n en segundo plano, puedes utilizar un gestor de procesos como PM2:
  
  ```bash
  sudo npm install pm2 -g
  pm2 start n8n -- -p 5678
  pm2 save
  pm2 startup
  ```
- ### Paso 5: Configurar el firewall
  Si tienes un firewall habilitado, asegúrate de permitir el tráfico en el puerto que utiliza n8n (por defecto, el puerto 5678).
  
  ```bash
  sudo ufw allow 5678
  ```
- ## Comandos Útiles de n8n
  
  | Comando                                   | Descripción                                                  |
  |-------------------------------------------|-------------------------------------------------------------|
  | `n8n`                                     | Inicia n8n en primer plano.                                 |
  | `pm2 start n8n -- -p 5678`               | Inicia n8n en segundo plano utilizando PM2 en el puerto 5678. |
  | `pm2 stop n8n`                           | Detiene n8n.                                               |
  | `pm2 restart n8n`                        | Reinicia n8n.                                             |
  | `pm2 list`                               | Muestra una lista de las aplicaciones gestionadas por PM2. |
  | `pm2 logs n8n`                           | Muestra los registros de n8n.                              |
  | `pm2 monit`                              | Muestra el monitor de PM2 para supervisar el rendimiento de las aplicaciones. |
  | `pm2 save`                               | Guarda la lista actual de procesos gestionados por PM2.    |
  | `pm2 startup`                            | Configura PM2 para que se inicie automáticamente al arrancar el sistema. |
- ## Configuración Básica de n8n
- ### Archivos de Configuración
  n8n no requiere una configuración compleja para empezar. Sin embargo, puedes personalizar su comportamiento mediante variables de entorno o archivos de configuración.
- ### Variables de Entorno
  Puedes configurar n8n utilizando variables de entorno. Por ejemplo, para cambiar el puerto en el que n8n escucha, puedes establecer la variable de entorno `N8N_PORT`:
  
  ```bash
  export N8N_PORT=5678
  n8n
  ```
- ## Ejemplo de Flujo de Trabajo
  Para crear un flujo de trabajo en n8n, sigue estos pasos:
  
  1. Abre la interfaz web de n8n en tu navegador. Por defecto, está disponible en `http://localhost:5678`.
  2. Haz clic en el botón "New Workflow" para crear un nuevo flujo de trabajo.
  3. Añade nodos a tu flujo de trabajo arrastrándolos desde el panel izquierdo.
  4. Configura cada nodo según tus necesidades.
  5. Conecta los nodos para definir el flujo de datos.
  6. Guarda el flujo de trabajo y actívalo para que se ejecute automáticamente.
- ## Página Dedicada
  Para más información sobre n8n, puedes visitar la página oficial de n8n.
  ```