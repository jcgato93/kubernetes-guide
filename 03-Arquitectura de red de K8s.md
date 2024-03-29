# ¿Cómo funciona la arquitectura de red de Kubernetes?


Arquitectura de K8s

## Nodo Master

- API Server: A lo que todo se conecta, los agentes, el CLI, el dashboard etc. Cuando se cae un nodo master es lo que se pierde. Se usa el algoritmo de ruft para algoritmo de elección.

- Scheduler: Cuando se deben crear un job, un pod en máquinas específicas, el scheduler se encarga de asignar las tareas y administrar los flujos de trabajos, revisando siempre las restricciones y los recursos disponibles.

- Controller Manager: Es un proceso que está en un ciclo de reconciliación constante buscando llegar al estado deseado con base al modelo declarativo con el que se le dan instrucciones a K8s.
++Tipos de controller manager: ++

Replica manager
Deployment manager
Service manager
…
- Etcd: Key value store que permite que el cluster este altamente disponible.


## Componentes muy importantes que viven en los nodos:

- Kubelet: Agente de kubernetes, se conecta con el control play y le pregunta que recursos (pods, contenedores) debo correr al scheduler via API Server. Monitorea los pods constantemente para saber si están vivos, los recursos disponibles etc y le comunica constantemente al scheduler via API Server.

- Kube-proxy: Se encarga de balancear el tráfico que corre en nuestros contenedores/servicios. Una vez llega una request se encarga de decidir a que pod y contenedor debe de ir.

Nodos == Minions

Todos los nodos y masters están conectados a una red física para poder hablarsen entre sí.