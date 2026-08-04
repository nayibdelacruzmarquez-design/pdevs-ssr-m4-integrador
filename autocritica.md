# Auto-crítica de Ejecución — Módulo 4

## 1. ¿Qué no probaste, y qué riesgo aceptaste al no probarlo?
No se realizaron pruebas de carga bajo tráfico concurrente sostenido ni pruebas de resistencia de la base de datos SQLite ante escrituras simultáneas masivas. El riesgo aceptado fue confiar en la simplicidad de SQLite para el alcance del prototipo integrador, asumiendo potencial bloqueo de tabla (database locking) si ocurren múltiples transacciones paralelas de escritura en producción.

## 2. ¿Dónde se rompe tu app con 10× usuarios? Sé concreto: qué componente, por qué.
La aplicación fallaría en la capa de persistencia de datos (`SQLite`). Con un incremento de 10× en usuarios concurrentes intentando realizar publicaciones o inicios de sesión simultáneos, la base de datos en archivo plano alcanzará el límite de bloqueos por escritura (`OperationalError: database is locked`), degradando la latencia y provocando respuestas HTTP 500 al no disponer de un pool de conexiones dedicado como PostgreSQL.

## 3. ¿En qué ADR te equivocaste? ¿Qué evidencia te faltó ver a tiempo?
El punto ciego inicial estuvo en el **ADR 4.2** y la estrategia de ejecución del servidor. Se asumió inicialmente que la estructura interna del paquete `src/app/` funcionaría de forma directa con el comando de arranque estándar de Flask, sin prever a tiempo la necesidad de un punto de entrada WSGI explícito (`src/wsgi.py`) exigido por servidores de producción como Gunicorn en un PaaS. La evidencia que faltó ver a tiempo fue la documentación de despliegue de paquetes Python en contenedores de producción.