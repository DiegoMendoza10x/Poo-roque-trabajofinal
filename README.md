# SYSALQUILERES — Sistema de gestión de alquileres

Proyecto académico de Programación Orientada a Objetos (POO 2026 · UPEU Juliaca). Aplicación para administrar el alquiler de departamentos mediante módulos de departamentos, inquilinos, contratos y pagos.

> **Contenido del repositorio:** código fuente y archivos necesarios para desarrollar y ejecutar el sistema. Los archivos generados de compilación, bases de datos locales y credenciales privadas deben mantenerse fuera del control de versiones.

## Funcionalidades

- **Inicio de sesión:** validación de usuarios y control de sesión.
- **Departamentos:** registro, búsqueda, edición y control de disponibilidad.
- **Inquilinos:** gestión de personas naturales y jurídicas, con validación de DNI.
- **Contratos:** registro, seguimiento y finalización; validación de fechas y prevención de contratos vigentes superpuestos.
- **Pagos:** registro y consulta de pagos, métodos de pago, descuentos e IGV.
- **Nota de venta:** vista previa e impresión térmica de 58 mm mediante impresora de Windows o puerto COM.
- **Persistencia:** base de datos H2 local y opción de conexión con PostgreSQL/Supabase.
- **Versión móvil:** aplicación Android complementaria (MVP).

## Tecnologías

| Tecnología | Uso |
|---|---|
| Java 21 | Lenguaje principal |
| JavaFX 21 + FXML | Interfaz de escritorio |
| Maven | Dependencias y compilación |
| H2 | Base de datos local predeterminada |
| PostgreSQL / Supabase | Alternativa de base de datos |
| HikariCP | Administración de conexiones |
| Jakarta Validation / Hibernate Validator | Validación de datos |
| jSerialComm | Comunicación con impresoras por puerto serie |
| Android / Gradle | Aplicación móvil complementaria |

## Arquitectura

La aplicación de escritorio está organizada por capas:

```text
FXML (vista)
   ↓
Controller
   ↓
Service (reglas de negocio)
   ↓
Repository (acceso a datos)
   ↓
Base de datos
```

Paquetes principales de Java: `components`, `config`, `controller`, `enums`, `exception`, `impresion`, `model`, `repository`, `service` y `util`.

## Requisitos

- JDK 21.
- Apache Maven 3.9 o superior.
- Para Android: Android SDK y JDK compatible con la configuración Gradle del proyecto.
- Para PostgreSQL/Supabase: acceso a una instancia y credenciales configuradas localmente.

## Ejecutar la aplicación de escritorio

Desde la carpeta que contiene `pom.xml`:

```bash
mvn javafx:run
```

Para compilar y empaquetar:

```bash
mvn -B -DskipTests package
```

La configuración predeterminada utiliza H2 local. En la primera ejecución, la aplicación crea la base y carga los datos de demostración según la configuración de `src/main/resources/application.properties`.

## Base de datos PostgreSQL / Supabase

Los scripts de creación de esquema están en `database/`. Para Supabase, sigue la guía `docs/SUPABASE.md`. Configura las credenciales mediante variables de entorno; **no escribas contraseñas reales en archivos que vayas a subir a GitHub**.

## Aplicación Android

El proyecto Android se encuentra en `android/`. Para compilar el APK de desarrollo o entrega, utiliza el Gradle Wrapper incluido en esa carpeta y sigue la guía del proyecto.

## Documentación del proyecto

- [Entregables del proyecto](ENTREGABLES.md)
- [Manual de usuario](docs/MANUAL_USUARIO.md)
- [Guía de exposición](docs/GUIA_EXPOSICION.md)
- [Descripción del código fuente](docs/CODIGO_FUENTE.md)
- [Empaquetamiento para Windows](docs/EMPAQUETAMIENTO.md)
- [Configuración de Supabase](docs/SUPABASE.md)
- [Impresión térmica de 58 mm](docs/IMPRESION_58MM.md)

## Organización y seguridad

El archivo `.gitignore` excluye resultados de compilación, configuraciones locales del IDE, bases de datos locales, APK generados, archivos de entorno y credenciales locales. No se versionan `target/`, `dist/`, `data/`, `android/local.properties` ni archivos con contraseñas.

Antes de publicar una versión de entrega, revisa que no haya tokens, claves, datos personales ni credenciales reales en el código, los documentos o el historial de Git.
