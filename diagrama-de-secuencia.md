# Diagrama de secuencia

Escenario principal: **el jugador resuelve una misión**, con un intento incorrecto y uno correcto, y avanza al siguiente escenario.

```mermaid
sequenceDiagram
    actor J as Jugador
    participant UI as Pantalla
    participant G as Juego
    participant M as Mision
    participant A as Actividad
    participant R as Retroalimentacion
    participant P as Progreso

    J->>UI: Presiona "Jugar"
    UI->>G: iniciarPartida()
    G->>UI: mostrarIntroduccion()
    J->>UI: Presiona "Comenzar"
    UI->>G: cargarMision(1)
    G->>M: iniciar()
    M->>UI: Muestra escenario y objetos
    M->>A: mostrar()
    A->>UI: Muestra pregunta o actividad

    loop Hasta responder correctamente
        J->>UI: Elige una respuesta
        UI->>A: validarRespuesta(opcion)
        alt Respuesta incorrecta
            A-->>UI: false
            UI->>R: mostrar(false)
            R->>UI: Mensaje de ánimo
            UI->>J: "Inténtalo de nuevo"
        else Respuesta correcta
            A-->>UI: true
            UI->>R: mostrar(true)
            R->>UI: Mensaje positivo
        end
    end

    UI->>M: completar()
    M->>P: actualizar()
    P->>UI: Muestra progreso (ej. 1 de 5)
    J->>UI: Presiona "Siguiente"
    UI->>G: avanzarSiguienteMision()
    G->>M: cargarMision(2)
```

Al completar la misión 5, `Juego` llama a `mostrarMensajeFinal()` y ofrece "Jugar de nuevo".
