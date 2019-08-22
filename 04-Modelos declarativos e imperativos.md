# Modelos declarativos e imperativos

Los control managers se encargan de estar en un loop constante de reconciliación y tratar de converger a ese estado deseado, ese es un sistema declarativo. Un sistema imperativo parece un sistema fácil de seguir y está compuesto por una serie de pasos que deben seguirse a rajatabla.

- Kubernetes hace énfasis en ser un sistema declarativo
- Declarativo: “Quiero una taza de té”
- Imperativo: “Hervir agua, agregar hojas de té y servir en una taza”
- Declarativo parece sencillo (siempre y cuando uno sepa cómo hacerlo)
- Todo en Kubernetes se crea desde un spec que describe cuál es el estado deseado del sistema
- Kubernetes constantemente converge con esa especificación