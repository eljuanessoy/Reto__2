# Reto__2
By Juan Esteban Molina Rey (eljuanessoy)

### En este diagrama de clases decidi represe3ntar un partido de basketball. En el diagrama podemos ver las relaciones con las que cuenta un partido, como lo serian los equipos, la cancha, las reglas, entre otras.

- El Partido tiene una duración definida por la clase Tiempo, está regido por las Reglas y cuenta con una Cancha.
- Los Jugadores interactúan usan el Uniforme.
- El Piso, el Aro y el Balon forman parte de la Cancha.
- El Entrenador dirige al Equipo

```mermaid
classDiagram
    PartidoBasketball "" <-- "" Tiempo : 
    PartidoBasketball "" <-- "" Reglas : 
    PartidoBasketball "" <-- "" Cancha : 
    PartidoBasketball "" <-- "" Equipo : 
    Entrenador "" --> "" Equipo : dirige
    Cancha "" --> "" Aro : 
    Cancha "" --> "" Piso : 
    Cancha "" --> "" Balon : 
    Equipo "" >-- "" Jugador : 
    Jugador "" <-- "" Uniforme : 

    
    class PartidoBasketball {
        +fecha: string
        +lugar: string
        +equipoLocal: string
        +equipoVisitante
        +marcadorLocal: int
        +marcadorVisitante: int
        +comenzarPartido()
        +finalizarPartido()
        +contadorPuntos()
    }

    class Entrenador {
        +nombre: string
        +añosExperiencia: int
        +planeaEstrategias()
        +dirigeJuego()
    }

    class Tiempo {
        +cuartos: float
        +duracion: int
        +tiempoMuerto: int
        +cronometrar()
    }
    
    class Reglas {
        +nombre: string
        +descripcion: string
        +validarRegla()
    }

    class Equipo {
        +nombre: string
        +jugadores: list
        +entrenador: string
        +titulos: int
        +entrenar()
        +añadirJugador()
    }

    class Cancha {
        +ubiacion: string
        +tipoDeSuperficie: string
        +disponerChancha()
    }

    class Aro {
        +altura: float
        +diametro: float
        +tipoDeRed: string
        +probarAro() 
    }

    class Piso {
        +dimensiones: string
        +tipoDeMadera: string
        +mantenerPiso()
    }

    class Jugador {
        +nombre: string
        +numero: int
        +posicion: string
        +altura: float
        +entrenar()
        +correr()
        +lanzar(Balon)
        +pasar(Balon)
    }

    class Balon {
        +medidas: float
        +peso: float
        +material: string
        +rebotar()
    }

    class Uniforme {
        +color: string
        +numero: int
        +nombreJugador: string
        +asignarUniforme(Jugador)
    }
