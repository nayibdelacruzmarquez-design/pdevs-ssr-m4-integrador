# ADR 4.7: Optimización de Consultas de Base de Datos (Prevención N+1)

* **Estatus:** Aceptado
* **Contexto:** Prevención de latencia y consultas redundantes al listado de publicaciones.
* **Decisión:** Empleo de `joinedload` en SQLAlchemy para eager loading de relaciones.
* **Alternativas:** Consultas perezosas (lazy loading) por iteración.
* **Consecuencias:** Reducción de $N+1$ consultas a una sola instrucción JOIN en SQL.
* **Evidencia:** Resultados de métricas capturados en `src/tests/spike.log`.