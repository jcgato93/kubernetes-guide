# De pods a contenedores

## Docker & Kubernetes

- Docker se encarga principalmente de gestionar los contenedores.
- Kubernetes es una evolución de proyectos de Google Borg & Omega.
- Kubernetes pertenece a la CNCF (Cloud Native Computing Foundation).
-Todos los cloud providers (GCP/AWS/Azure/DO) ofrecen servicios de managed k8s utilizando Docker como su container runtime
- Es la plataforma más extensiva para orquestación de servicios e infraestructura


## Kubernetes en la práctica

- K8s permite correr varias réplicas y asegurarse que todas se encuentren funcionando.
- Provee un balanceador de carga interno o externo automáticamente para nuestros servicios.
- Definir diferentes mecanismos para hacer roll-outs de código.
- Políticas de scaling automáticas.
- Jobs batch.
- Correr servicios con datos stateful.

Todos los contenedores que viven dentro de un mismo Pod comparten el mismo segmento de red.