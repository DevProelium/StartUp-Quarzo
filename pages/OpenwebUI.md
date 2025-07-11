# Open WebUI

Open WebUI es una plataforma de inteligencia artificial autoalojada, extensible, rica en características y fácil de usar, diseñada para operar completamente sin conexión. Es compatible con varios ejecutores de modelos de lenguaje grande (LLM) como Ollama y APIs compatibles con OpenAI, e incluye un motor de inferencia integrado para RAG (Retrieval-Augmented Generation), lo que la convierte en una potente solución para el despliegue de IA.
- ## Instalación
- ### Requisitos Previos
  
  Antes de instalar Open WebUI, asegúrate de tener Docker instalado en tu sistema. Si no lo tienes, puedes seguir la guía de instalación de Docker.
- ### Comandos de Instalación
  
  Puedes instalar Open WebUI utilizando Docker. Aquí tienes algunos comandos útiles para diferentes configuraciones:
- #### Instalación básica con Docker:
  
  ```bash
  docker run -d -p 8080:8080 -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
  ```
- #### Instalación con soporte para GPU Nvidia:
  
  ```bash
  docker run -d -p 3000:8080 --gpus all --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:cuda
  ```
- #### Instalación con Ollama incluido:
  
  ```bash
  docker run -d -p 3000:8080 -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama
  ```
- #### Instalación con API de OpenAI:
  
  ```bash
  docker run -d -p 3000:8080 -e OPENAI_API_KEY=your_secret_key -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
  ```
- ## Configuración
- ### Variables de Entorno
  
  Open WebUI utiliza varias variables de entorno para ajustar su comportamiento. Aquí tienes algunas de las más importantes:
  
  | Variable           | Descripción                                                  |
  |--------------------|-------------------------------------------------------------|
  | PORT               | Establece el puerto en el que se ejecutará Open WebUI.     |
  | WEBUI_AUTH         | Habilita o deshabilita la autenticación. Establecer a False desactiva la autenticación. |
  | DATA_DIR           | Especifica el directorio donde se almacenarán los datos de Open WebUI. |
  | OPENAI_API_KEY     | Clave API para acceder a los servicios de OpenAI.          |
- ### Ejemplo de Configuración con Docker Compose
  
  Si prefieres usar Docker Compose, aquí tienes un ejemplo de archivo `docker-compose.yml`:
  
  ```yaml
  version: '3.8'
  
  services:
  open-webui:
    image: ghcr.io/open-webui/open-webui:main
    container_name: open-webui
    ports:
      - "8080:8080"
    volumes:
      - open-webui:/app/backend/data
    environment:
      - DATA_DIR=/app/backend/data
    restart: always
  
  volumes:
  open-webui:
  ```
  
  Para iniciar Open WebUI con Docker Compose, usa los siguientes comandos:
  
  ```bash
  docker-compose up -d
  ```
- ## Comandos Útiles
  
  | Comando                                      | Descripción                                   |
  |----------------------------------------------|-----------------------------------------------|
  | `docker ps`                                  | Lista los contenedores en ejecución.         |
  | `docker logs open-webui`                     | Muestra los logs del contenedor Open WebUI.  |
  | `docker stop open-webui`                     | Detiene el contenedor Open WebUI.            |
  | `docker start open-webui`                    | Inicia el contenedor Open WebUI.             |
  | `docker restart open-webui`                  | Reinicia el contenedor Open WebUI.           |
  | `docker rm open-webui`                       | Elimina el contenedor Open WebUI.            |
  | `docker rmi ghcr.io/open-webui/open-webui:main` | Elimina la imagen de Open WebUI.             |
- ## Recursos Adicionales
  
  Para más información y configuraciones avanzadas, puedes consultar la documentación oficial de Open WebUI.