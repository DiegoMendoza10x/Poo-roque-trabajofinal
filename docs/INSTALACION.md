# Instalación y ejecución

## Requisitos para la aplicación de escritorio

- JDK 21.
- Apache Maven 3.9 o superior.
- Windows, Linux o macOS con soporte para JavaFX.

## Obtener el proyecto

Clona el repositorio y entra a la carpeta del proyecto:

```bash
git clone https://github.com/DiegoMendoza10x/Poo-roque-trabajofinal.git
cd Poo-roque-trabajofinal
```

Comprueba que `pom.xml` esté en la carpeta actual.

## Ejecutar

```bash
mvn javafx:run
```

## Compilar

```bash
mvn -B -DskipTests package
```

Los archivos generados se guardan en `target/`, que está excluida del control de versiones.

## Base de datos

La configuración predeterminada de la aplicación utiliza H2 local. Revisa `src/main/resources/application.properties` para identificar los parámetros de conexión. Para utilizar PostgreSQL o Supabase, sigue [SUPABASE.md](SUPABASE.md) y configura los datos de acceso mediante variables de entorno.

No subas contraseñas, tokens ni archivos locales de configuración al repositorio.

## Aplicación Android

La aplicación móvil está dentro de `android/`. En Windows, desde esa carpeta:

```powershell
.\gradlew.bat assembleDebug
```

En Linux/macOS:

```bash
./gradlew assembleDebug
```

Se requiere Android SDK correctamente instalado y configurado. Los APK y directorios de compilación no se versionan; se generan localmente.

## Problemas frecuentes

- Si Maven no está reconocido, instala Maven o utiliza el ejecutable `mvn.cmd` en Windows.
- Si JavaFX no inicia, verifica que se esté usando JDK 21 y ejecuta la aplicación mediante el objetivo Maven indicado.
- Si no conecta a PostgreSQL/Supabase, revisa URL, usuario, contraseña, SSL y variables de entorno.
