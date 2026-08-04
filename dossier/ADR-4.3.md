# ADR 4.3: Arquitectura de Persistencia y Modelado de Datos

* **Estatus:** Aceptado
* **Contexto:** Elección del ORM y motor de base de datos para desarrollo e integración.
* **Decisión:** Utilizar Flask-SQLAlchemy con motor SQLite integrado.
* **Alternativas:** PostgreSQL nativo en la nube o MongoDB.
* **Consecuencias:** Despliegue sin dependencias externas complejas manteniendo compatibilidad relacional.
* **Evidencia:** Prueba de concepto en local y portabilidad del archivo de base de datos.