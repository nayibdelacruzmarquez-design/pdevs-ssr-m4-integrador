# ADR 4.5: Mecanismo de Prevención CSRF y Validación de Formulario

* **Estatus:** Aceptado
* **Contexto:** Protección contra ataques Cross-Site Request Forgery en formularios.
* **Decisión:** Integración de Flask-WTF con tokens CSRF inyectados en formularios.
* **Alternativas:** Validaciones manuales por encabezados custom.
* **Consecuencias:** Mitigación automática de ataques CSRF sin fricción en el usuario.
* **Evidencia:** Estándares OWASP de protección en formularios HTML.