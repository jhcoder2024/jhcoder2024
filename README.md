# Ing. Jorge Hernandez

Senior Software Developer dedicated to creating highly scalable, 
maintainable backends and clean architectural patterns.

- 🏗️ **Architectural Focus:** Clean Architecture, Hexagonal, and SOLID principles.
- 🐳 **Infrastructure:** Containerization (Docker, Kubernetes) and Database Migrations.
- 📱 **Explorations:** Cross-platform mobile solutions (Flutter) and Autonomous Agent Workflows.

## 🛠️ Tech Stack & Tools
[Aquí puedes incluir badges de tecnologías: .NET, NestJS, Postgres, Docker, Git]

## 📁 Featured Projects
### 📱 Localizador Móvil de Emergencia
*Desarrollo Mobile de Alta Prioridad | Flutter & Android Native Integrations*

Aplicación móvil orientada a la seguridad y respuesta inmediata ante emergencias. El proyecto está diseñado para garantizar la emisión de alertas de auxilio eficientes incluso bajo condiciones de conectividad limitada.

*   **Retos de Ingeniería Resueltos:** Integración directa con el ciclo de vida de Android mediante el **Android SDK**, orquestación de permisos en tiempo real y consumo de capacidades nativas del hardware para el envío automatizado de mensajería de texto (**SMS**) con coordenadas geográficas precisas.
*   **Stack:** Flutter, Dart, Android SDK Core, Location & SMS Native APIs.
### 📄 eContratosApi

[![Backend](https://img.shields.io/badge/Architecture-Clean_Architecture-blue.svg)](#)
[![Docker](https://img.shields.io/badge/Containerization-Docker_Compose-blue.svg)](#)

`eContratosApi` es una solución empresarial diseñada para la gestión, auditoría y notificación automatizada de contratos. El sistema mitiga el acoplamiento tecnológico mediante la separación estricta de responsabilidades, garantizando alta testabilidad y escalabilidad ante incrementos en el volumen de transacciones.

#### 🏗️ Arquitectura y Patrones de Diseño

El núcleo del proyecto está implementado bajo los principios de **Clean Architecture** (Arquitectura Limpia) y diseño guiado por el dominio (DDD simplificado), dividiéndose en las siguientes capas:

*   **Domain:** Contiene las entidades de negocio puras, excepciones de dominio y contratos de interfaces de abstracción primarias. Libre de dependencias externas.
*   **Application:** Implementa los casos de uso del sistema. Orquesta el flujo de datos desde y hacia el dominio utilizando el patrón **CQRS** (Command Query Responsibility Segregation) para optimizar los tiempos de lectura y escritura de forma independiente.
*   **Infrastructure:** Aloja las implementaciones concretas de acceso a datos (Patrón Repositorio), integraciones con proveedores de mensajería externos (PigeonPost) y persistencia.
*   **API / Presentation:** Punto de entrada de la aplicación expuesto a través de controladores REST estructurados, manejando inyección de dependencias nativa y middleware global para el manejo unificado de excepciones.

#### 🛠️ Stack Tecnológico

*   **Core:** [.NET / NestJS] utilizando principios **SOLID** avanzados.
*   **Persistencia:** [PostgreSQL / SQL Server / MySQL] con estrategias de aislamiento de transacciones y optimización de consultas.
*   **Mensajería/Notificaciones:** Integración desacoplada con clientes de mensajería y colas de tareas.
*   **DevOps & Entorno:** Docker y Docker-Compose para la replicación exacta de entornos de desarrollo y producción.

#### 🚀 Decisiones de Ingeniería Destacadas

*   **Desacoplamiento de Notificaciones:** En lugar de acoplar la lógica de contratos con el servicio de envío de correos/SMS, se implementó un patrón de eventos o inversión de dependencias. Si el cliente de mensajería cambia en el futuro, la regla de negocio permanece intacta.
*   **Estrategia de Migraciones Robustas:** Control estricto del versionamiento de la base de datos a través de scripts ordenados e incrementales, asegurando la consistencia del esquema en despliegues automatizados y previniendo la pérdida de datos en producción.
*   **Validación de Capas:** Validación rigurosa de datos en la capa de Aplicación mediante Fluent Validation / interceptores, bloqueando cargas útiles corruptas antes de que impacten el estado del dominio.

### 🚗 club_vehiculos

[![Database](https://img.shields.io/badge/Backend_As_A_Service-Supabase-green.svg)](#)
[![UI/UX](https://img.shields.io/badge/UI_Layout-Responsive_Maquetation-orange.svg)](#)
[![Migrations](https://img.shields.io/badge/Database_Migrations-v0001__v0045-blue.svg)](#)

`club_vehiculos` es una plataforma integral de gestión y visualización de perfiles automotrices. El sistema centraliza la administración de flotas o clubes de vehículos, ofreciendo una experiencia altamente fluida en el cliente mediante interfaces responsivas e interactivas, respaldada por una arquitectura de persistencia robusta y versionada de forma estricta.

#### 🏗️ Enfoque y Decisiones de Ingeniería

Este proyecto fue diseñado bajo estándares profesionales enfocados en la mantenibilidad a largo plazo, la consistencia de los datos y la optimización del rendimiento en el frontend.

##### 1. Control de Cambios en Base de Datos (Estrategia de Migraciones)
Para evitar la degradación del esquema y garantizar la replicabilidad del entorno, la base de datos no se maneja mediante interfaces gráficas directas.
* **Estructura Incremental:** Se implementó una estrategia rígida de control de versiones de bases de datos utilizando el sistema de migraciones nativo de **Supabase**.
* **Evolución del Esquema:** El ciclo de vida de los datos está documentado secuencialmente desde la migración inicial `0001` hasta la `0045`, aislando mediante lenguaje de definición de datos (**DDL**) la creación de tablas, triggers, funciones almacenadas y políticas de seguridad por filas (RLS - Row Level Security).

##### 2. UI Maquetación Responsiva & Componentización
El frontend prioriza el rendimiento visual y la adaptabilidad a cualquier factor de forma (Mobile, Tablet y Desktop).
* **Profile Cards Dinámicas:** Se diseñó un sistema modular de tarjetas de perfil de vehículos que renderizan dinámicamente información técnica del automóvil (marca, modelo, año, especificaciones) optimizando el uso de layouts fluidos.
* **Carga de Recursos Eficiente:** Estructuración de componentes atómicos reutilizables que mitigan los re-renderizados innecesarios del lado del cliente al interactuar con filtros de búsqueda en tiempo real.

#### 🛠️ Stack Tecnológico

* **Base de Datos y Autenticación:** Supabase (PostgreSQL avanzado, Triggers, RLS Policies, Functions).
* **Control de Persistencia:** Supabase CLI para la orquestación e integración de esquemas.
* **Frontend:** [Indicar Framework aquí, ej. Flutter, React o Vue] estructurado con metodologías de diseño limpio y CSS/Styles responsivos.

#### 📂 Estructura Clave de Persistencia (DDL)

Las migraciones del proyecto gestionan de forma atómica:
1. **Entidades Relacionales:** Relación estricta de integridad referencial entre usuarios (`profiles`), vehículos (`vehicles`), imágenes y registros de mantenimiento.
2. **Seguridad Avanzada (RLS):** Políticas PostgreSQL que garantizan que los usuarios solo puedan mutar o visualizar vehículos asociados a su club o cuenta autorizada, reduciendo vulnerabilidades a nivel de API.
