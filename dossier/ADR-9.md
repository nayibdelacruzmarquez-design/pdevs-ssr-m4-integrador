# ADR 9: Adaptaciones de Arquitectura durante la Construcción

* **Estatus:** Aceptado
* **Contexto:** Ajustes requeridos al pasar de decisiones teóricas a la construcción en producción.
* **Decisión:** Adición de un punto de entrada explícito `src/wsgi.py` y configuración de `Procfile`.
* **Alternativas:** Intentar ejecutar `app.py` directamente con el servidor de desarrollo de Flask.
* **Consecuencias:** Compatibilidad completa con el proxy inverso y manejador de procesos de Render.
* **Evidencia:** Log de compilación exitosa en Render Dashboard (`is live!`).