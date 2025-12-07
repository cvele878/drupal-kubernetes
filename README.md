# Proyecto Drupal en Kubernetes

Este proyecto contiene los manifiestos necesarios para desplegar una aplicación Drupal en un clúster de Kubernetes. La aplicación incluye un servidor web, una base de datos y el propio Drupal, todos configurados para ejecutarse en el espacio de nombres `drupal-lab`.

## Contenido

- **`namespace.yaml`**: Define el espacio de nombres `drupal-lab` donde se desplegarán los recursos.
- **`web-server-deployment.yaml`**: Configura el despliegue del servidor web basado en Nginx.
- **`load-balancer.yaml`**: Configura un servicio de tipo `LoadBalancer` para exponer el servidor web.
- **`database-deployment.yaml`**: Configura el despliegue de la base de datos MariaDB.
- **`database-service.yaml`**: Configura un servicio de tipo `ClusterIP` para la base de datos.
- **`drupal-deployment.yaml`**: Configura el despliegue de la aplicación Drupal.
- **`drupal-service.yaml`**: Configura un servicio de tipo `ClusterIP` para la aplicación Drupal.

## Requisitos

- Un clúster de Kubernetes configurado.
- `kubectl` instalado y configurado para interactuar con el clúster.
- Opcional: Un proveedor de nube que soporte servicios de tipo `LoadBalancer` (por ejemplo, AWS, GCP, Azure).

## Despliegue

1. Crear el espacio de nombres:
   ```bash
   kubectl apply -f namespace.yaml