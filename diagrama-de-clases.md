# Diagrama de clases

```mermaid
classDiagram
    class Juego {
        -Jugador jugador
        -List~Mision~ misiones
        -int misionActual
        +iniciarPartida()
        +mostrarIntroduccion()
        +cargarMision(indice)
        +avanzarSiguienteMision()
        +reiniciarPartida()
        +mostrarMensajeFinal()
    }

    class Jugador {
        -String nombre
        -int misionesCompletadas
        +completarMision()
        +obtenerProgreso() int
        +reiniciarProgreso()
    }

    class Mision {
        -int id
        -String titulo
        -String tema
        -boolean completada
        -Escenario escenario
        -Actividad actividad
        +iniciar()
        +completar()
        +estaCompletada() boolean
    }

    class Escenario {
        -String nombre
        -String imagenFondo
        -List~ObjetoEscenario~ objetos
        +mostrar()
    }

    class ObjetoEscenario {
        -String nombre
        -String imagen
        -boolean esCorrecto
    }

    class Actividad {
        -String enunciado
        -List~Opcion~ opciones
        +mostrar()
        +validarRespuesta(opcion) boolean
    }

    class Opcion {
        -String texto
        -boolean esCorrecta
    }

    class Retroalimentacion {
        -String mensajePositivo
        -String mensajeAnimo
        +mostrar(esCorrecta)
    }

    class Progreso {
        -int total
        -int completadas
        +actualizar()
        +mostrar()
    }

    Juego "1" *-- "1" Jugador
    Juego "1" *-- "5" Mision
    Juego "1" --> "1" Progreso
    Juego ..> Retroalimentacion : usa
    Mision "1" *-- "1" Escenario
    Mision "1" *-- "1" Actividad
    Escenario "1" o-- "*" ObjetoEscenario
    Actividad "1" *-- "*" Opcion
```

## Notas de diseño

- Las misiones, escenarios y preguntas son **datos** que se cargan en `Mision`, `Escenario` y `Actividad`. Así se pueden agregar o modificar sin reconstruir el juego (RNF-08).
- `Juego` controla el flujo y `Progreso` lleva el conteo de misiones completadas para mostrarlo al jugador (RF-10).
- `Actividad.validarRespuesta()` es el único punto donde se decide si una respuesta es correcta, lo que mantiene la validación consistente (RNF-04).
