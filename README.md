# proyecto-final
# Proyecto Final: Orquestación con Kubernetes

## Integrantes
Jhojan Dario Mosquera, 
Kristal sanchez, 
Santiago Fajardo, 
Nelli Cordoba

## Pre-requisitos y Configuración Base
Para garantizar la compatibilidad y el rendimiento del cluster, se configuró el entorno bajo los siguientes parámetros:

- **Motor de contenedores:** Se utilizó Docker como driver principal para Minikube, permitiendo una gestión eficiente de los recursos del host.
- **Acceso remoto:** Se validó la conexión interna y la correcta ejecución del nodo mediante `minikube ssh`, garantizando que el Control Plane tuviera comunicación estable con el host virtualizado.

## Home
Este proyecto documenta la implementación de un cluster de Kubernetes utilizando Minikube para el despliegue de aplicaciones web escalables.

## Componentes

### Componente 3: Orquestación con Kubernetes
En esta etapa, realizamos el despliegue de una aplicación Nginx con las siguientes características:
- **Deployment:** 3 réplicas (escalado manual).
- **Service:** Tipo NodePort (puerto 30007).

### Documentación Completa
Puedes consultar el reporte detallado con todas las capturas de pantalla aquí:
[Ver reporte PDF](documento_de_evidencias.pdf)

### Configuración del Entorno (Docker & SSH)
Para asegurar el correcto despliegue del cluster, se configuró el motor de Docker como driver de Minikube y se validó la comunicación con el nodo:

```bash
sudo systemctl status docker
minikube start --driver=docker
minikube ssh -- docker info
minikube ssh -- docker images
minikube start --driver=docker
kubectl apply -f nginx-deployment.yaml
kubectl scale deployment nginx-deployment --replicas=3
