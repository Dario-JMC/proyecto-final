# Proyecto Final: Implementación de Infraestructura y Orquestación

## Integrantes
- Jhojan Dario Mosquera
- Kristal Sanchez
- Santiago Fajardo
- Nelli Cordoba

## Home
Este proyecto documenta la implementación integral de un sistema basado en Linux y Kubernetes, desde la virtualización de servidores hasta el despliegue de aplicaciones web escalables.

---

## Componente 1: Virtualización con Linux
En esta etapa, se realizó la infraestructura base mediante la virtualización de dos nodos en VirtualBox.

[📋 Ver reporte PDF](evidencias.pdf).

### Conectividad y Acceso Remoto
Para validar la red entre la VM1 (Gráfica) y la VM2 (Consola), se configuró el acceso mediante SSH:
```bash
# Probar conexión desde VM1 hacia VM2 (reemplazar IP)
ssh usuario_vm2@192.168.x.x

# Verificar estado del servicio SSH
sudo systemctl status ssh

# Verificar Docker e iniciar cluster
sudo systemctl status docker
minikube start --driver=docker

# Validar conectividad con el nodo
minikube ssh -- docker info
# Aplicar despliegue
kubectl apply -f manifests/nginx-deployment.yaml

# Escalar a 3 réplicas
kubectl scale deployment nginx-deployment --replicas=3

# Verificar pods
kubectl get pods
