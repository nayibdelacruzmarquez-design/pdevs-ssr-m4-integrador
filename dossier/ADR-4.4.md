# ADR 4.4: Estrategia de Autenticación y Control de Acceso (RBAC)

* **Estatus:** Aceptado
* **Contexto:** Requisito de autenticación con al menos 2 roles de usuario.
* **Decisión:** Gestión de sesiones vía Flask Session con roles asignados (`admin` y `user`).
* **Alternativas:** Autenticación JWT o OAuth2 externo.
* **Consecuencias:** Simplicidad en plantillas HTML manteniendo separación estricta de permisos.
* **Evidencia:** OWASP Cheat Sheet para manejo seguro de sesiones en servidor.