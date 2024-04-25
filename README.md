# README - Pipeline de Jenkins

## Tabla de Contenidos
1. [Introducción](#introducción)
2. [Pre-requisitos](#pre-requisitos)
3. [Instalación](#instalación)
4. [Configuración de Jenkins](#configuración-de-jenkins)
5. [Creación del Pipeline](#creación-del-pipeline)
6. [Ejecución del Pipeline](#ejecución-del-pipeline)
7. [Troubleshooting](#troubleshooting)
8. [Contribuidores](#contribuidores)

## Introducción
Este documento proporciona las instrucciones necesarias para crear y ejecutar un pipeline en Jenkins. Un pipeline en Jenkins es una serie de pasos que permite automatizar el proceso de integración y despliegue de software.

## Pre-requisitos
Antes de comenzar, necesitas tener lo siguiente:
- Una instancia de Jenkins instalada y en funcionamiento.
- Acceso administrativo en Jenkins.
- Una cuenta de GitHub o similar para el repositorio de código fuente.

## Configuración de Jenkins
1. **Configurar el entorno Jenkins:**
   - Acceder a Jenkins con tus credenciales.
   - Configurar las variables de entorno necesarias para los proyectos que vas a automatizar.

## Creación del Pipeline
1. **Crear un nuevo Item en Jenkins:**
   - Ir a la página principal de Jenkins.
   - Hacer clic en "Nuevo Item".
   - Seleccionar "Pipeline" y poner un nombre al pipeline.
   - Hacer clic en "OK".

2. **Configurar el pipeline:**
   - En la sección de configuración del pipeline, seleccionar "Pipeline script from SCM" en la opción de definición. Esto permite que Jenkins utilice un script de pipeline almacenado en un sistema de control de versiones.
   - Como sistema de control de versiones (SCM), seleccionar "Git".
   - En el campo "Repository URL", ingresar la URL del repositorio de GitHub que contiene tu Jenkinsfile. La URL debe tener el formato `https://github.com/usuario/repositorio.git`.
   - Si el repositorio es privado, necesitarás configurar las credenciales. Hacer clic en "Add" > "Jenkins" bajo el campo de credenciales, y luego seleccionar "Jenkins Credential Provider". Aquí puedes agregar tus credenciales de GitHub usando el tipo "Username with password". Ingresar tu nombre de usuario de GitHub y un token de acceso personal como contraseña.
   - En el campo "Branches to build", especificar la rama del repositorio que contiene el Jenkinsfile, por ejemplo, `main` o `master`.
   - Configurar adicionalmente los hooks de webhook en GitHub para que Jenkins pueda recibir notificaciones de cambios en el repositorio y disparar builds automáticamente. Esto se realiza en la configuración del repositorio de GitHub bajo la sección "Webhooks".

## Ejecución del Pipeline
1. **Ejecutar el Pipeline:**
   - Ir al dashboard del pipeline creado.
   - Hacer clic en "Build Now" para iniciar la ejecución del pipeline.
