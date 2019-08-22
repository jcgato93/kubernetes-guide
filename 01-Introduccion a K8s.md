# Introduccion a Kubernetes (K8s)

Kubernetes
Desde el principio, Kubernetes fue diseñado para ser un entorno para la creación de aplicaciones distribuidas de contenedores. El objetivo principal de Kubernetes es un sistema para la construcción, el funcionamiento y la gestión de sistemas distribuidos.

Además se basa en la experiencia de muchos años de Google trabajando con los contenedores de Linux. Es, en cierto modo, una réplica de lo que Google ha estado haciendo durante mucho tiempo, pero, esta vez, adaptado a Dockers, entonces aporta esa experiencia en la forma de organizar y desplegar una aplicación en contenedores.

Otra buena característica de Kubernetes es que se puede configurar el controlador para mantener activos el mismo número de contenedores, es decir, si por algún motivo se detuviese algún contenedor, se creará un nuevo contenedor con una copia casi exacta, del 99%.

Y por último (que no quiero decir que no tenga más características) es el escalado ya sea “hacia arriba” o “hacia abajo”; con Kubernetes es fácil, solo se tiene que especificar la cantidad de nuevas aplicaciones y si quieres hacia arriba o hacia abajo a través de un comando.

en cuanto a Docker Swarm, es la herramienta nativa para el cluster de Docker. Con Docker Swarm tenemos lo que llamaremos Swarm Master que será el responsable del cluster, también tendremos nodos que debe ser accesible por el Master y cada uno de ellos contendrá uno o varios contenedores.

Al contrario que Kubernetes, Swarm es un “esfuerzo” por parte de Docker para extender la API de Docker existente para hacer que un conjunto de máquinas se vean como una sola API de Docker.

