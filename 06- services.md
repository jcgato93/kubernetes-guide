# Services 

los services (servicios) es una forma de acceder a los contenedores 
exponiendo una IP ya sea para comunicacion interna de los nodos o una 
publica para dar acceso a las aplicaciones

Existen varios tipos de servicios , pero los mas comunes para exponer los 
contenedores son :

ClusterIP (default)

    expone el servicio en una IP interna en el clúster. Este tipo hace que solo se pueda acceder al Servicio desde el clúster.

NodePort 

    expone el servicio en el mismo puerto de cada nodo seleccionado en el clúster utilizando NAT. Hace que un servicio sea accesible desde fuera del clúster mediante <NodeIP>:<NodePort>. Superconjunto de ClusterIP.

LoadBalancer 

    crea un valanceador de carga externo en la nube actual (si es compatible) y asigna una IP externa fija al Servicio. Superconjunto de NodePort.

ExternalName 

    expone el Servicio utilizando un nombre arbitrario (especificado externalNameen la especificación) al devolver un registro CNAME con el nombre. No se usa proxy. Este tipo requiere v1.7 o superior de kube-dns.


Un servicio enruta el tráfico a través de un conjunto de pods. Los servicios son la abstracción que permite que las cápsulas mueran y se repliquen en Kubernetes sin afectar su aplicación. Kubernetes Services maneja el descubrimiento y el enrutamiento entre pods dependientes (como los componentes frontend y backend en una aplicación).    



## Crear servicio utilizando yaml

```yaml
apiVersion: v1
kind: Service
metadata:
    name: wordpress
spec:
    type: NodePort
    ports:
    - port: 80 #puerto que expone
      targetPort: 80 
      nodePort: 30000 # puerto al que apunta dentro del contenedor
    selector:
        role: wordpress # indica que los pods con role == wordpress se les debe enviar el trafico

```

### Implementar servicio

        $ kubectl -n <namespace> apply -f <nombre archivo>

### Para ver los servicios

        $ kubectl -n <namespace> get svc