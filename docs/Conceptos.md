_¿Cual es el proposito de diseño de Gradle doFirst y doLast?_
Tiene que ver con la extensibilidad, la reutilización y evitar la duplicacion. Las tareas integradas se pueden extender como:
task CopyAndThen(type: Copy) {
   doFirst {
      println "this is before the actual copy"
   }
   doLast {
      println "this is after the actual copy"
   }
}

El segundo escenario comun que viene a la mente es con compilaciones de multiples proyectos, donde puede tener una definicion de tarea en la parte superior del proyecto con un comportamiento comun:
allprojects {
    task myTask_a {
        doFirst {...}
    }
}
Y luego los proyectos especificos pueden extender eso. Basicamente, la tarea tiene una lista de los cierres que se deben ejecutar y la eleccion de los controles doFirst o doLast hasta que extremo de la lista va la insercion.