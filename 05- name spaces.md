# Name spaces 

Los namespace son una seracion logica de nuestra arquitectura

En caso de que se necesite diferentes ambientes como testing, develop, production


para crear un name space utilizando el formato yaml
```yaml
kind: Namespace
apiVersion: v1
metadata:
    name: testing
```
usando el comando 

        kubectl apply -f  <NOMBRE ARCHIVO>


para listar los namespace 

        kubectl get ns