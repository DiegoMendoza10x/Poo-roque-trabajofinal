# Arquitectura de SYSALQUILERES

## Descripción

SYSALQUILERES es una aplicación de gestión de alquileres de departamentos. La aplicación de escritorio utiliza Java 21, JavaFX y FXML, con acceso a datos mediante repositorios y reglas de negocio encapsuladas en servicios.

## Flujo de una operación

```text
Vista FXML → Controller → Service → Repository → Base de datos
```

- **Vista (FXML/CSS):** presenta formularios, tablas y controles.
- **Controller:** recibe las acciones del usuario y coordina la vista con los servicios.
- **Service:** aplica validaciones y reglas de negocio.
- **Repository:** ejecuta las operaciones de persistencia.
- **Model:** representa las entidades del sistema.
- **Config/Util:** concentra configuración, conexión, sesión y utilidades compartidas.

## Paquetes principales

El código Java se organiza bajo `pe.edu.upeu.alquileres`:

| Paquete | Responsabilidad |
|---|---|
| `components` | Diálogos y componentes visuales reutilizables |
| `config` | Contexto de dependencias y configuración de base de datos |
| `controller` | Controladores de pantallas y módulos |
| `enums` | Estados y tipos utilizados por el sistema |
| `exception` | Excepciones de negocio |
| `impresion` | Preparación e impresión de notas de venta |
| `model` | Entidades y modelos |
| `repository` | Acceso a datos |
| `service` | Reglas y operaciones del sistema |
| `util` | Formato, sesión y validaciones |

## Módulos funcionales

1. Departamentos.
2. Inquilinos.
3. Contratos.
4. Pagos y nota de venta.

## Persistencia

La configuración permite utilizar H2 para desarrollo local o PostgreSQL/Supabase mediante parámetros y variables de entorno. Los scripts SQL se encuentran en `database/`; consulta [SUPABASE.md](SUPABASE.md) para la alternativa en la nube.

## Principio de diseño

La separación por capas busca mantener las responsabilidades diferenciadas: la interfaz no debe contener consultas SQL ni reglas de negocio complejas, y el repositorio no debe encargarse de la presentación.
