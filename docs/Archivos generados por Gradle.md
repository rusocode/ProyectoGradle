## Gradle Wrapper
* gradlew: El script de shell que los usuarios de Unix pueden efectuar para ejecutar tareas de Gradle.
* gradlew.bat: El bat script que los usuarios de Windows pueden efectuar para ejecutar tareas de Gradle.
* gradle/wrapper/gradle-wrapper.jar: JAR ejecutable del contenedor; aqui es donde reside el codigo contenedor.
* gradle/wrapper/gradle-wrapper.properties - Un archivo de propiedades para configurar el contenedor.
	- distributionUrles: Especifica que version de Gradle desea usar para sus compilaciones y de donde descargarla.

## Otros
* gradle.properties
	- org.gradle.daemon=true: Permite configurar Gradle para usar un Deamon evitando iniciar la maquina virtual de java en cada compilacion. Esto mejora el rendimiento para el inicio de la JVM, pero puede tener un espacio de almacenamiento maximo demasiado pequeño, por lo tanto tiene sentido aumentarlo para Gradle.
	- org.gradle.jvmargs=-Xms128m -Xmx1500m: Especifica el tamaño de memoria (inicial y maxima) para la JVM en Gradle.