# ReplicationController

Un ReplicationController garantiza que se ejecute un número específico de réplicas de pod en cualquier momento. En otras palabras, un ReplicationController se asegura de que un pod o un conjunto homogéneo de pods esté siempre activo y disponible.

## Cómo funciona un controlador de replicación

Si hay demasiados pods, ReplicationController termina los pods adicionales. Si hay muy pocos, el ReplicationController inicia más pods. A diferencia de los pods creados manualmente, los pods mantenidos por un ReplicationController se reemplazan automáticamente si fallan, se eliminan o se finalizan. Por ejemplo, sus pods se vuelven a crear en un nodo después de un mantenimiento disruptivo, como una actualización del kernel. Por esta razón, debe usar un ReplicationController incluso si su aplicación requiere solo un pod. Un ReplicationController es similar a un supervisor de procesos, pero en lugar de supervisar procesos individuales en un solo nodo, ReplicationController supervisa múltiples pods en múltiples nodos.

ReplicationController a menudo se abrevia como "rc" o "rcs" en discusión, y como acceso directo en los comandos de kubectl.

Un caso simple es crear un objeto ReplicationController para ejecutar de manera confiable una instancia de un Pod indefinidamente. Un caso de uso más complejo es ejecutar varias réplicas idénticas de un servicio replicado, como servidores web.


## Ejecutando un ejemplo ReplicationController

```yaml
apiVersion: v1
kind: ReplicationController
metadata:
  name: nginx
spec:
  replicas: 3
  selector:
    app: nginx
  template:
    metadata:
      name: nginx
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx
        ports:
        - containerPort: 80
```


## Aplicar ReplicationController 

- Aplicar

        $ kubectl apply -f <nombre archivo>

- Listar los Replication Controller

        $ kubectl -n <namespace> get rc


