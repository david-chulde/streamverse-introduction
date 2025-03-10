## Microservices APIS

### 1. Microservicios de Autenticación y Usuarios (sv-ms-auth) - (Rust) - (PostgreSQL o MySQL) // correction JS

1. **Servicio de Autenticación (sv-ms-auth-session)** | port: 3000
   - Login, logout, y generación de tokens JWT.
   - Manejo de sesiones y renovación de tokens.
   - Recuperación de Contraseña mediante OTP o token.
2. **Servicio de Gestión de Cuentas de perfil (sv-ms-auth-profile)** | port: 3001
   - Actualización de perfiles.
   - Eliminación de cuentas.
3. **Servicio de recuperación de Cuenta y número de intentos (sv-ms-auth-recovery)** | port: 3002
   - Intentos de Recuperación de Contraseña.
   - Recuperación de Cuenta bloqueada.
   - Lista de Preguntas de Seguridad del usuario.

### 2. Microservicios de Contenido (Videos) (sv-ms-video) - (JS NestJs) - (MongoDB o DynamoDB)

4. **Servicio de Subida de Videos (sv-ms-video-upload)**
   - Procesamiento y almacenamiento de videos.
   - Gestión de metadatos (título, descripción, etiquetas).
5. **Servicio de Feed de Videos (sv-ms-video-feed)**
   - Generación de recomendaciones basadas en historial y preferencias.
   - Paginación y clasificación de videos.
6. **Servicio de Reproducción de Videos (sv-ms-video-play)**
   - Streaming adaptativo.
   - Control de calidad y ancho de banda.
7. **Servicio de Gestión de Categorías y Etiquetas (sv-ms-video-category)**
   - Creación y actualización de categorías.
   - Relación entre videos y etiquetas.
8. **Servicio de Moderación de Contenido (sv-ms-video-report)**
   - Revisión de videos reportados.
   - Aplicación de políticas de la comunidad.

### 3. Microservicios de Interacción Social (sv-ms-social) - (Java & SprintBoot)

9. **Servicio de Comentarios (sv-ms-social-comment)** port 3009
   - Creación, edición y eliminación de comentarios.
10. **Servicio de Likes y Dislikes (sv-ms-social-like)** port 3010
    - Seguimiento de likes y dislikes
    - Estadísticas para métricas de popularidad.
11. **Servicio de Suscripciones (sv-ms-social-subscription)**
    - Seguimiento de canales.
    - Notificaciones para nuevos videos.
12. **Servicio de Notificaciones (sv-ms-social-notification)**
    - Notificaciones push para nuevos videos, comentarios, y actividades.
    - Configuración de preferencias de notificación.
??. **Servicio de Reportar un Comentario (sv-ms-social-report-comment)**
   - Revisión de comentarios reportados.
### 4. Microservicios de Monetización (sv-ms-monetization) - (Python & Django)

13. **Servicio de Pagos y Suscripciones Premium (sv-ms-monetization-payment)**
    - Procesamiento de pagos (integración con pasarelas como Stripe o PayPal).
    - Gestión de planes de suscripción.
14. **Servicio de Anuncios (sv-ms-monetization-ads)**
    - Inserción de anuncios en videos.
    - Gestión de campañas publicitarias.
15. **Servicio de Reparto de Ganancias (sv-ms-monetization-report)**
    - Cálculo de ingresos para creadores.
    - Generación de reportes de ganancias.

### 5. Microservicios de Análisis y Estadísticas (sv-ms-statistic) - (Golang & Gin)

16. **Servicio de Análisis de Videos (sv-ms-statistic-video)**
    - Métricas de visualización (vistas, tiempo de reproducción, retención).
    - Generación de reportes para creadores.
17. **Servicio de Análisis de Usuarios (sv-ms-statistic-user)**
    - Seguimiento del comportamiento de usuarios.
    - Estadísticas para personalización del feed.

### 6. Microservicios de Infraestructura (sv-ms-configuration) - (JS & NestJs)

18. **Servicio de Almacenamiento (sv-ms-configuration-storage)**
    - Gestión de almacenamiento para videos, miniaturas y archivos adjuntos.
    - Integración con servicios de almacenamiento en la nube (como AWS S3).
19. **Servicio de Gestión de Logs (sv-ms-configuration-log)**
    - Registro de eventos y errores en los microservicios.
    - Monitoreo de la aplicación.
20. **Servicio de Gestión de Configuración (sv-ms-configuration-management)**
    - Gestión centralizada de variables de entorno y configuraciones para todos los microservicios.
    - Sincronización de configuraciones dinámicas.

---

## Bases de Datos a implementar

1. **Usuarios y Autenticación**: Base de datos relacional (PostgreSQL o MySQL).
2. **Videos y Metadatos**: Base de datos NoSQL (MongoDB o DynamoDB).
3. **Comentarios**: Base de datos relacional.
4. **Likes y Dislikes**: Base de datos en memoria (Redis) para rapidez.
5. **Notificaciones**: Base de datos de eventos (Kafka o RabbitMQ).
6. **Pagos**: Base de datos relacional con alta seguridad.
7. **Anuncios**: Base de datos NoSQL.
8. **Estadísticas de Usuarios**: Base de datos analítica (ClickHouse o BigQuery).
9. **Logs**: Base de datos especializada en logs (Elasticsearch).
10. **Configuraciones**: Base de datos clave-valor (Consul o etcd).
