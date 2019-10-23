# Deployments

Una Deployment proporciona actualizaciones declarativas para Pods y ReplicaSets .

Describe un estado deseado en un Deployment y el Controlador de implementación cambia el estado real al estado deseado a una velocidad controlada. Puede definir implementaciones para crear nuevos ReplicaSets o eliminar Deployments existentes y adoptar todos sus recursos con nuevos Deployments.


Ejemplo 
```yaml
apiVersion: extensions/v1beta1
kind: Deployment
metadata:
  name: hello
spec:
  replicas: 3
  template:
    metadata:
      labels:
        role: hello
    spec:
      containers:
      - name: hello
        image: gcr.io/google-samples/hello-app:2.0
        imagePullPolicy: IfNotPresent        
        ports:
        - containerPort: 8080
```


## Escalar 

para listar los deployments

    $ kubectl -n <namespace> get deployments

para escalar el numero de pods utilizando un deployment

    $ kubectl scale --replicas=3 deployment/<nombre deployment>