# Backend Despachos - Innovatech Chile (Proyecto Semestral)

Este repositorio contiene la API REST del microservicio de **Despachos**, desarrollado en Spring Boot y Java. Forma parte de la arquitectura de microservicios desplegada en AWS.

## Arquitectura y Despliegue
El servicio se encuentra dockerizado y alojado en **Amazon ECR**. Su ejecución es orquestada por **Amazon ECS (Fargate)**, permitiendo un despliegue Serverless con alta disponibilidad. Se comunica con el Frontend a través de un Application Load Balancer (ALB).

## Pipeline CI/CD automatizado
Mediante GitHub Actions, cualquier cambio subido a la rama `main` activa un pipeline que:
1. Autentica de forma segura con AWS (vía Secrets).
2. Construye la imagen Docker desde la subcarpeta correspondiente.
3. Sube la imagen actualizada a Amazon ECR.
4. Actualiza el servicio en ECS (Fargate) sin interrupción del servicio.

## Endpoints Principales
* Documentación Swagger/OpenAPI disponible en la ruta: `/swagger-ui.html` (o configuración local).
