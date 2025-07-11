# Qdrant

Qdrant es una base de datos de vectores y un motor de búsqueda de vectores de código abierto escrito en Rust. Proporciona un servicio rápido y escalable de búsqueda de similitud de vectores con una API conveniente.
- ## Instalación
- ### Requisitos Previos
  
  Antes de instalar Qdrant, asegúrate de tener Docker instalado y en ejecución en tu sistema.
- ### Comandos de Instalación
  
  Puedes instalar Qdrant utilizando Docker. Aquí tienes algunos comandos útiles para diferentes configuraciones:
- #### Instalación básica con Docker:
  
  ```bash
  docker pull qdrant/qdrant
  docker run -p 6333:6333 -p 6334:6334 -v $(pwd)/qdrant_storage:/qdrant/storage qdrant/qdrant
  ```
- #### Instalación con una clave API:
  
  ```bash
  docker run -d -p 6333:6333 -e QDRANT__SERVICE__API_KEY="your-api-key-here" -v "${PWD}/qdrant_storage:/qdrant/storage:z" qdrant/qdrant
  ```
- ## Configuración
- ### Variables de Entorno
  
  Qdrant utiliza varias variables de entorno para ajustar su comportamiento. Aquí tienes algunas de las más importantes:
  
  | Variable                             | Descripción                                                  |
  |--------------------------------------|-------------------------------------------------------------|
  | QDRANT__SERVICE__API_KEY             | Establece la clave API para acceder a los servicios de Qdrant. |
  | QDRANT__STORAGE__STORAGE_PATH        | Especifica el directorio donde se almacenarán los datos de Qdrant. |
  | QDRANT__SERVICE__GRPC_PORT           | Establece el puerto gRPC para Qdrant.                       |
  | QDRANT__SERVICE__HTTP_PORT           | Establece el puerto HTTP para Qdrant.                       |
- ### Archivo de Configuración
  
  Puedes personalizar la configuración de Qdrant utilizando un archivo de configuración. Aquí tienes un ejemplo de archivo de configuración `production.yaml`:
  
  ```yaml
  service:
  api_key: "your-api-key-here"
  grpc_port: 6334
  http_port: 6333
  
  storage:
  storage_path: "/qdrant/storage"
  ```
  
  Para usar este archivo de configuración, puedes montarlo en el contenedor Docker:
  
  ```bash
  docker run -d -p 6333:6333 -p 6334:6334 -v $(pwd)/qdrant_storage:/qdrant/storage -v $(pwd)/custom_config.yaml:/qdrant/config/production.yaml qdrant/qdrant
  ```
- ## Comandos Útiles
  
  | Comando                                 | Descripción                                                  |
  |-----------------------------------------|-------------------------------------------------------------|
  | `docker pull qdrant/qdrant`            | Descarga la última imagen de Qdrant desde Docker Hub.      |
  | `docker run -p 6333:6333 -p 6334:6334 -v $(pwd)/qdrant_storage:/qdrant/storage qdrant/qdrant` | Ejecuta un contenedor Qdrant con los puertos 6333 (REST API) y 6334 (gRPC API) expuestos. |
  | `docker ps`                             | Lista los contenedores en ejecución.                        |
  | `docker logs <container_id>`           | Muestra los logs del contenedor Qdrant.                    |
  | `docker stop <container_id>`           | Detiene el contenedor Qdrant.                              |
  | `docker start <container_id>`          | Inicia el contenedor Qdrant.                               |
  | `docker restart <container_id>`        | Reinicia el contenedor Qdrant.                             |
  | `docker rm <container_id>`             | Elimina el contenedor Qdrant.                              |
  | `docker rmi qdrant/qdrant`             | Elimina la imagen de Qdrant.                               |
- ## Recursos Adicionales
  
  Para más información y configuraciones avanzadas, puedes consultar la documentación oficial de Qdrant.