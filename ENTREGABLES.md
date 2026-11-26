# Entregables del proyecto final — SYSALQUILERES

Este archivo sirve como índice para revisar el proyecto y ubicar sus componentes principales.

| N.º | Entregable | Ubicación |
|---|---|---|
| 1 | Manual de usuario | [docs/MANUAL_USUARIO.md](docs/MANUAL_USUARIO.md) |
| 2 | Código fuente de escritorio | [src/](src/) y [pom.xml](pom.xml) |
| 3 | Aplicación móvil complementaria | [android/](android/) |
| 4 | Scripts de base de datos | [database/](database/) |
| 5 | Guía de exposición | [docs/GUIA_EXPOSICION.md](docs/GUIA_EXPOSICION.md) |
| 6 | Documentación técnica del código | [docs/CODIGO_FUENTE.md](docs/CODIGO_FUENTE.md) |
| 7 | Guía de empaquetamiento de Windows | [docs/EMPAQUETAMIENTO.md](docs/EMPAQUETAMIENTO.md) |
| 8 | Configuración de PostgreSQL/Supabase | [docs/SUPABASE.md](docs/SUPABASE.md) |
| 9 | Impresión de nota de venta de 58 mm | [docs/IMPRESION_58MM.md](docs/IMPRESION_58MM.md) |

## Compilar los entregables

Los ejecutables y paquetes de instalación son productos generados; no son necesarios para revisar el código fuente. Para generarlos, sigue las instrucciones de [docs/EMPAQUETAMIENTO.md](docs/EMPAQUETAMIENTO.md). El APK se construye desde la carpeta `android/` con el Gradle Wrapper.

## Qué revisar primero

1. Leer el [README](README.md) para conocer el propósito, las tecnologías y los módulos.
2. Consultar el [manual de usuario](docs/MANUAL_USUARIO.md) para recorrer las funciones.
3. Revisar la estructura de [código fuente](docs/CODIGO_FUENTE.md) y la arquitectura por capas.
4. Revisar los scripts SQL y la guía de configuración de base de datos.
5. Seguir la guía de exposición para comprender el funcionamiento de los módulos.

## Seguridad

No incluir contraseñas de bases de datos, tokens, archivos `.env`, bases de datos locales ni archivos de configuración específicos de una computadora. Las credenciales de demostración, si se utilizan en un entorno local, deben cambiarse antes de cualquier despliegue real.
