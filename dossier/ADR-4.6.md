# ADR 4.6: Arquitectura de Plantillas e Interfaz Visual

* **Estatus:** Aceptado
* **Contexto:** Requisito de renderizado de vistas con herencia HTML.
* **Decisión:** Uso de Jinja2 con `base.html` y estilos Bootstrap 5 vía CDN.
* **Alternativas:** Frontend desacoplado en React o Vue.
* **Consecuencias:** Cero compilación de assets en cliente y código modular fácil de mantener.
* **Evidencia:** Documentación oficial de Jinja2 sobre inheritance patterns.