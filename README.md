# SYSALQUILERES

Sistema de escritorio para la gestión de alquiler de departamentos, desarrollado con **Java 21, JavaFX, FXML y Maven**.

## Módulos principales

- **Departamentos:** registro, consulta, edición y control de disponibilidad.
- **Inquilinos:** administración de personas naturales y jurídicas.
- **Contratos:** registro y seguimiento de contratos de alquiler, con validaciones de fechas y disponibilidad.
- **Pagos:** registro y consulta de pagos, métodos de pago y generación de notas de venta para impresión térmica de 58 mm.
- **Acceso de usuarios:** inicio de sesión y control de sesión.
- **Base de datos:** soporte para H2 local y PostgreSQL/Supabase.

## Tecnologías

- Java 21
- JavaFX 21 y FXML
- Maven
- H2 y PostgreSQL
- HikariCP
- Jakarta Validation / Hibernate Validator

## Estructura esperada

```text
SysAlquileres/
├── src/
│   ├── main/
│   └── test/
├── database/
├── docs/
├── scripts/
├── android/
├── pom.xml
├── .gitignore
└── README.md
```

## Requisitos

- JDK 21
- Apache Maven
- Conexión a la base de datos configurada para el entorno de ejecución

## Compilación

Desde la carpeta que contiene `pom.xml`:

```bash
mvn clean package
```

## Seguridad

No publiques contraseñas, tokens, archivos de configuración con credenciales ni bases de datos locales. Configura las credenciales y variables de entorno en tu propio equipo.

## Documentación

La carpeta `docs/` contiene el manual de usuario, la guía de exposición, la documentación del código y las instrucciones de configuración. Consulta esos archivos una vez que el código del proyecto esté incorporado al repositorio.
