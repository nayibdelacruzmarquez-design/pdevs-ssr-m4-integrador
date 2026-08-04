# ADR 4.8: Selección de la Plataforma de Despliegue (PaaS)

* **Estatus:** Aceptado
* **Contexto:** Requisito de despliegue en PaaS sin requerir tarjeta de crédito en capa gratuita.
* **Decisión:** Despliegue en Render usando Gunicorn como servidor WSGI de producción.
* **Alternativas:** PythonAnywhere, Vercel o túneles locales (descartados por regla).
* **Consecuencias:** Servidor independiente con build reproducible y URL viva constante.
* **Evidencia:** Documentación oficial de Render para aplicaciones WSGI en Python.