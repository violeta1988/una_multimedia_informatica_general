# una_multimedia_informatica_general

//Gonzalez Violeta

#include <iostream>
#include <string>
#include <vector>
#include <algorithm>  // Para std::fill
using namespace std;

// Declaración de la matriz que representa la pantalla
vector<vector<char>> pantalla(40, vector<char>(120, ' '));

// Prototipos
void mostrarMenu();
void mostrarHistoria();
void instrucciones();
void creditos();
void iniciarJuego(string nombreJugador);

string nombreJugador;

int main() {
  int opcion = 0;
  bool salir = false;

  while (!salir) {
    mostrarMenu();
    cin >> opcion;

    switch (opcion) {
      case 1:
        cout << "\nAntes de empezar, ¿cómo te llamás? ";
        getline(cin >> ws, nombreJugador);
        cout << "\nBienvenidx, " << nombreJugador << "! Veamos si podés rescatar a los gatos...\n";
        iniciarJuego(nombreJugador);
        break;

      case 2:
        instrucciones();
        break;

      case 3:
        creditos();
        break;

      case 4:
        cout << "\nHas decidido abandonar la misión. ¡Hasta la próxima!\n";
        salir = true;
        break;

      default:
        cout << "\nOpción inválida. Intenta nuevamente.\n";
        break;
    }

    if (!salir) {
      cout << "\nPresioná una tecla y luego ENTER para volver al menú...\n";
      char pausa;
      cin >> pausa;
    }
  }

  return 0;
}

void mostrarMenu() {

cout << "                                                    ██░▀██████████████▀░██\n";
cout << "                                                 　　█▌▒▒░████████████░▒▒▐█\n";
cout << "                                                 　　█░▒▒▒░██████████░▒▒▒░█\n";
cout << "                                                 　　▌░▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒░▐\n";
cout << "                                                 　　░▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒░\n";
cout << "                                                 　 ███▀▀▀██▄▒▒▒▒▒▒▒▄██▀▀▀██\n";
cout << "                                                 　 ██░░░▐█░▀█▒▒▒▒▒█▀░█▌░░░█\n";
cout << "                                                 　 ▐▌░░░▐▄▌░▐▌▒▒▒▐▌░▐▄▌░░▐▌\n";
cout << "                                                 　　█░░░▐█▌░░▌▒▒▒▐░░▐█▌░░█\n";
cout << "                                                 　　▒▀▄▄▄█▄▄▄▌░▄░▐▄▄▄█▄▄▀▒\n";
cout << "                                                 　　░░░░░░░░░░└┴┘░░░░░░░░░\n";
cout << "                                                 　　██▄▄░░░░░░░░░░░░░░▄▄██\n";
cout << "                                                 　　████████▒▒▒▒▒▒████████\n";
cout << "                                                 　　█▀░░███▒▒░░▒░░▒▀██████\n";
cout << "                                                 　　█▒░███▒▒╖░░╥░░╓▒▐█████\n";
cout << "                                                 　　█▒░▀▀▀░░║░░║░░║░░█████\n";
cout << "                                                 　　██▄▄▄▄▀▀┴┴╚╧╧╝╧╧╝┴┴███\n";
cout << "                                                 　　██████████████████████\n";

cout << "                                      --------------------------------------------------\n";
cout << "                                      --------------------------------------------------\n";
cout << "                                               *****    GATOS ENCERRADOS   *****        \n";
cout << "                                      --------------------------------------------------\n";
cout << "                                      --------------------------------------------------\n";
cout << "                                                    1. Iniciar juego\n";
cout << "                                                    2. Instrucciones\n";
cout << "                                                    3. Creditos\n";
cout << "                                                    4. Salir\n";
cout << "                                                                                       \n";
cout << "                                                   ELEGI UNA OPCION...\n";
cout << "                                                                                       \n";
cout << "                                              ---------------------------------\n";
cout << "                                              ---------------------------------\n";
   
}

void mostrarHistoria() {
  cout << "\nTe acercás a una casa antigua y oscura...\n";
  cout << "Dicen que adentro vive un veterinario siniestro.\n";
  cout << "Se rumorea que encierra gatos inocentes para hacer experimentos.\n";
  cout << "Tu misión es entrar a la casa, encontrar a los gatos y liberarlos...\n";
  cout << "¡Antes de que sea demasiado tarde!\n\n";
}

void instrucciones() {
  cout << "\nINSTRUCCIONES:\n";
  cout << " - Resolve los acertijos para encontrar y liberar a los gatos.\n";
  cout << " - Utiliza el teclado para jugar.\n\n";
}

void creditos() {
  cout << "\nCREDITOS:\n";
  cout << " Este juego fue creado por Violeta Gonzalez.\n";
  cout << " Trabajo práctico número 1 para la materia Informática 1 del prof. Tirigall.\n\n";
  cout << " Gracias por jugar (ﾐ^ᆽ^ﾐ).\n\n";
}

void iniciarJuego(string nombreJugador) {
  cout << "\nEl juego está por comenzar...\n";
  cout << "\n¡Mucha suerte y fuerza, " << nombreJugador << ", para rescatarlos de esas malvadas manos!\n";

  cout << "\nLlegás a una casa antigua, tenebrosa, con el jardín lleno de estatuas de gatos.\n";
  cout << "La puerta principal está cerrada con un candado electrónico.\n";
  cout << "El candado tiene un mensaje: INGRESA LA CLAVE PARA ABRIR\n";

  int intentos = 0;
  const int maxIntentos = 3;
  char respuesta;
  bool acertado = false;

  while (intentos < maxIntentos && !acertado) {
    cout << "\n¿Qué clave intentás? (Intento " << (intentos + 1) << " de " << maxIntentos << ")\n";
    cout << "a) 708\n";
    cout << "b) 444\n";
    cout << "c) 678\n";
    cout << "d) 101\n";
    cout << "Elegí una opción (a/b/c/d): ";
    cin >> respuesta;

    if (respuesta == 'd' || respuesta == 'D') {
      cout << "\n¡Correcto! la puerta se abre lentamente...\n";
      acertado = true;
    } else {
      cout << "\nClave incorrecta.\n";
      intentos++;
    }
  }

  if (!acertado) {
    cout << "\nUsaste los 3 intentos. El candado permanece cerrado y no podés entrar a la casa.\n";
    cout << "\nGAME OVER\n";
    cout << "███████████████████████████████████\n";
    cout << "████████████ GAME OVER ███████████\n";
    cout << "███████████████████████████████████\n";
    cout << "█████████████▒▒▒▒▒▒▒▒▒█████████████\n";
    cout << "█████████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█████████\n";
    cout << "███████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒███████\n";
    cout << "██████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒██████\n";
    cout << "█████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█████\n";
    cout << "█████▒▒▒▒█▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█▒▒▒▒█████\n";
    cout << "████▒▒▒▒███▒▒▒▒▒▒▒▒▒▒▒▒▒███▒▒▒▒████\n";
    cout << "███▒▒▒▒██████▒▒▒▒▒▒▒▒▒██████▒▒▒▒███\n";
    cout << "███▒▒▒███▐▀███▒▒▒▒▒▒▒███▀▌███▒▒▒███\n";
    cout << "███▒▒▒██▄▐▌▄███▒▒▒▒▒███▄▐▌▄██▒▒▒███\n";
    cout << "███▒▒▒▒██▌███▒▒▒█▒█▒▒▒███▐██▒▒▒▒███\n";
    cout << "██▒▒▒▒▒▒███▒▒▒▒██▒██▒▒▒▒███▒▒▒▒▒▒██\n";
    cout << "█▒▒▒▒▒▒▒▒█▒▒▒▒██▒▒▒██▒▒▒▒█▒▒▒▒▒▒▒▒█\n";
    cout << "█▒▒▒▒▒▒▒▒▒▒▒▒▒█▒▒▒▒▒█▒▒▒▒▒▒▒▒▒▒▒▒▒█\n";
    cout << "█▒▒▒▒█▒▒█▒▒▒▒██▒▒▒▒▒██▒▒▒▒█▒▒█▒▒▒▒█\n";
    cout << "██▒▒▒█▒▒█▒▒▒▒█▒██▒██▒█▒▒▒▒█▒▒█▒▒▒██\n";
    cout << "███▒█▒▒█▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█▒▒█▒███\n";
    cout << "█████▒▒█▒▒▒▐███████████▌▒▒▒█▒▒█████\n";
    cout << "███████▒▒▒▐█▀██▀███▀██▀█▌▒▒▒███████\n";
    cout << "███████▒▒▒▒█▐██▐███▌██▌█▒▒▒▒███████\n";
    cout << "███████▒▒▒▒▒▐▒▒▐▒▒▒▌▒▒▌▒▒▒▒▒███████\n";
    cout << "████████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒████████\n";
    cout << "████████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒████████\n";
    cout << "█████████▒▒█▒█▒▒▒█▒▒▒█▒█▒▒█████████\n";
    cout << "█████████▒██▒█▒▒▒█▒▒▒█▒██▒█████████\n";
    cout << "██████████████▒▒███▒▒██████████████\n";
    cout << "██████████████▒█████▒██████████████\n";
    cout << "███████████████████████████████████\n";
    cout << "███████████████████████████████████\n";
    return;
  }

  // Segundo acertijo: jaula con gatos
  cout << "\nEntraste con cautela. El interior está oscuro y hay un silencio de inocentes.\n";
  cout << "Al avanzar, te encontrás con una jaula donde están encerrados 2 gatitos.\n";

  intentos = 0;
  acertado = false;

  while (intentos < maxIntentos && !acertado) {
    cout << "\nLa jaula tiene otro candado digital con la siguiente pregunta:\n";
    cout << "\"¿Qué porcentaje del día duermen los gatos?\"\n";
    cout << "a) 60\n";
    cout << "b) 90\n";
    cout << "c) 70\n";
    cout << "d) 45\n";
    cout << "Elegí una opción (a/b/c/d): ";
    cin >> respuesta;

    if (respuesta == 'c' || respuesta == 'C') {
      cout << "\n¡Correcto! Liberaste 2 gatitos!!\n";
      acertado = true;
    } else {
      cout << "\nRespuesta incorrecta. Jaula bloqueada.\n";
      intentos++;
    }
  }

  if (!acertado) {
    cout << "\nUsaste los 3 intentos. \n";
    cout << "███████████████████████████████████\n";
    cout << "████████████ GAME OVER ███████████\n";
    cout << "███████████████████████████████████\n";
    cout << "█████████████▒▒▒▒▒▒▒▒▒█████████████\n";
    cout << "█████████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█████████\n";
    cout << "███████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒███████\n";
    cout << "██████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒██████\n";
    cout << "█████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█████\n";
    cout << "█████▒▒▒▒█▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█▒▒▒▒█████\n";
    cout << "████▒▒▒▒███▒▒▒▒▒▒▒▒▒▒▒▒▒███▒▒▒▒████\n";
    cout << "███▒▒▒▒██████▒▒▒▒▒▒▒▒▒██████▒▒▒▒███\n";
    cout << "███▒▒▒███▐▀███▒▒▒▒▒▒▒███▀▌███▒▒▒███\n";
    cout << "███▒▒▒██▄▐▌▄███▒▒▒▒▒███▄▐▌▄██▒▒▒███\n";
    cout << "███▒▒▒▒██▌███▒▒▒█▒█▒▒▒███▐██▒▒▒▒███\n";
    cout << "██▒▒▒▒▒▒███▒▒▒▒██▒██▒▒▒▒███▒▒▒▒▒▒██\n";
    cout << "█▒▒▒▒▒▒▒▒█▒▒▒▒██▒▒▒██▒▒▒▒█▒▒▒▒▒▒▒▒█\n";
    cout << "█▒▒▒▒▒▒▒▒▒▒▒▒▒█▒▒▒▒▒█▒▒▒▒▒▒▒▒▒▒▒▒▒█\n";
    cout << "█▒▒▒▒█▒▒█▒▒▒▒██▒▒▒▒▒██▒▒▒▒█▒▒█▒▒▒▒█\n";
    cout << "██▒▒▒█▒▒█▒▒▒▒█▒██▒██▒█▒▒▒▒█▒▒█▒▒▒██\n";
    cout << "███▒█▒▒█▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█▒▒█▒███\n";
    cout << "█████▒▒█▒▒▒▐███████████▌▒▒▒█▒▒█████\n";
    cout << "███████▒▒▒▐█▀██▀███▀██▀█▌▒▒▒███████\n";
    cout << "███████▒▒▒▒█▐██▐███▌██▌█▒▒▒▒███████\n";
    cout << "███████▒▒▒▒▒▐▒▒▐▒▒▒▌▒▒▌▒▒▒▒▒███████\n";
    cout << "████████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒████████\n";
    cout << "████████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒████████\n";
    cout << "█████████▒▒█▒█▒▒▒█▒▒▒█▒█▒▒█████████\n";
    cout << "█████████▒██▒█▒▒▒█▒▒▒█▒██▒█████████\n";
    cout << "██████████████▒▒███▒▒██████████████\n";
    cout << "██████████████▒█████▒██████████████\n";
    cout << "███████████████████████████████████\n";
    cout << "███████████████████████████████████\n";

    return;
  }

  cout << "\nAvanzaste hacia la siguiente habitación...\n";
  cout << "\noh! Nuevo obstaculo a resolver!¡\n";
  cout << "\nOtra jaula con 5 gatos, pobrecitos!...\n";
  cout << "\nFrente a vos hay una consola que clausura la jaula, esta tiene tres palancas de colores: una roja, una azul y una verde.\n";
  cout << "\nEl mensaje des la misma dice:\n";
  cout << "\n- Para liberar a los michis tienes que combinar 2 palancas y activarà la cerradura -\n";
  cout << "\nPiensa bien que elegir..\n";
  
  // aca usamos AND y OR combinados 
  bool palancaRoja, palancaAzul, palancaVerde;
  intentos = 0;
  acertado = false;

  while (intentos < 3 && !acertado) {
    cout << "\nIntento " << (intentos + 1) << " de 3\n";
    cout << "¿Activás la palanca ROJA? (1 = sí, 0 = no): ";
    cin >> palancaRoja;
    cout << "¿Activás la palanca AZUL? (1 = sí, 0 = no): ";
    cin >> palancaAzul;
    cout << "¿Activás la palanca VERDE? (1 = sí, 0 = no): ";
    cin >> palancaVerde;

    if (palancaRoja && (palancaAzul || palancaVerde)) {
      cout << "\n¡Click! La jaula se abriò! los gatos salen corriendo hacia la libertad! iujuu!\n";
      acertado = true;
    } else {
      cout << "\nAy, no! te has confundido de palanca.\n";
      intentos++;
    }
  }

  if (!acertado) {
    cout << "\nFallaste los 3 intentos. El mecanismo se traba y la jaula no se puede volver a abrir...\n";
    cout << "GAME OVER\n";
    cout << "███████████████████████████████████\n";
    cout << "████████████ GAME OVER ███████████\n";
    cout << "███████████████████████████████████\n";
    cout << "█████████████▒▒▒▒▒▒▒▒▒█████████████\n";
    cout << "█████████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█████████\n";
    cout << "███████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒███████\n";
    cout << "██████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒██████\n";
    cout << "█████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█████\n";
    cout << "█████▒▒▒▒█▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█▒▒▒▒█████\n";
    cout << "████▒▒▒▒███▒▒▒▒▒▒▒▒▒▒▒▒▒███▒▒▒▒████\n";
    cout << "███▒▒▒▒██████▒▒▒▒▒▒▒▒▒██████▒▒▒▒███\n";
    cout << "███▒▒▒███▐▀███▒▒▒▒▒▒▒███▀▌███▒▒▒███\n";
    cout << "███▒▒▒██▄▐▌▄███▒▒▒▒▒███▄▐▌▄██▒▒▒███\n";
    cout << "███▒▒▒▒██▌███▒▒▒█▒█▒▒▒███▐██▒▒▒▒███\n";
    cout << "██▒▒▒▒▒▒███▒▒▒▒██▒██▒▒▒▒███▒▒▒▒▒▒██\n";
    cout << "█▒▒▒▒▒▒▒▒█▒▒▒▒██▒▒▒██▒▒▒▒█▒▒▒▒▒▒▒▒█\n";
    cout << "█▒▒▒▒▒▒▒▒▒▒▒▒▒█▒▒▒▒▒█▒▒▒▒▒▒▒▒▒▒▒▒▒█\n";
    cout << "█▒▒▒▒█▒▒█▒▒▒▒██▒▒▒▒▒██▒▒▒▒█▒▒█▒▒▒▒█\n";
    cout << "██▒▒▒█▒▒█▒▒▒▒█▒██▒██▒█▒▒▒▒█▒▒█▒▒▒██\n";
    cout << "███▒█▒▒█▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█▒▒█▒███\n";
    cout << "█████▒▒█▒▒▒▐███████████▌▒▒▒█▒▒█████\n";
    cout << "███████▒▒▒▐█▀██▀███▀██▀█▌▒▒▒███████\n";
    cout << "███████▒▒▒▒█▐██▐███▌██▌█▒▒▒▒███████\n";
    cout << "███████▒▒▒▒▒▐▒▒▐▒▒▒▌▒▒▌▒▒▒▒▒███████\n";
    cout << "████████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒████████\n";
    cout << "████████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒████████\n";
    cout << "█████████▒▒█▒█▒▒▒█▒▒▒█▒█▒▒█████████\n";
    cout << "█████████▒██▒█▒▒▒█▒▒▒█▒██▒█████████\n";
    cout << "██████████████▒▒███▒▒██████████████\n";
    cout << "██████████████▒█████▒██████████████\n";
    cout << "███████████████████████████████████\n";
    cout << "███████████████████████████████████\n";
    return;
  }
  // Última prueba: escaneo de iris
  cout << "\nAvanzás hacia el fondo de la casa y encontrás la última habitación...\n";
  cout << "En el centro hay una gran jaula con ¡10 gatitos más!\n";
  cout << "Pero frente a la jaula hay una computadora con una cámara y un mensaje del veterinario:\n";
  cout << "\"Para abrir esta jaula, deberás escanear tu iris y entregarme algo de información personal.\"\n";

  char decision;
  bool decisionValida = false;

  while (!decisionValida) {
    cout << "\n¿Aceptás escanear tu iris y compartir información para liberar a los gatos? (s/n): ";
    cin >> decision;

    if (decision == 's' || decision == 'S') {
      cout << "\nLa cámara escanea tu iris... ¡clic! La jaula se abre automáticamente.\n";
      cout << "¡Has liberado a 10 gatitos más! Corrés con ellos hacia la salida.\n";
      cout << "\n¡¡FELICITACIONES, " << nombreJugador << ", HAS GANADO EL JUEGO!!\n";
cout << "░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░\n";
cout << "░░░░░░░░░░▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄░░░░░░░░░\n";
cout << "░░░░░░░░▄▀░░░░░░░░░░░░▄░░░░░░░▀▄░░░░░░░\n";
cout << "░░░░░░░░█░░▄░░░░▄░░░░░░░░░░░░░░█░░░░░░░\n";
cout << "░░░░░░░░█░░░░░░░░░░░░▄█▄▄░░▄░░░█░▄▄▄░░░\n";
cout << "░▄▄▄▄▄░░█░░░░░░▀░░░░▀█░░▀▄░░░░░█▀▀░██░░\n";
cout << "░██▄▀██▄█░░░▄░░░░░░░██░░░░▀▀▀▀▀░░░░██░░\n";
cout << "░░▀██▄▀██░░░░░░░░▀░██▀░░░░░░░░░░░░░▀██░\n";
cout << "░░░░▀████░▀░░░░▄░░░██░░░▄█░░░░▄░▄█░░██░\n";
cout << "░░░░░░░▀█░░░░▄░░░░░██░░░░▄░░░▄░░▄░░░██░\n";
cout << "░░░░░░░▄█▄░░░░░░░░░░░▀▄░░▀▀▀▀▀▀▀▀░░▄▀░░\n";
cout << "░░░░░░█▀▀█████████▀▀▀▀████████████▀░░░░\n";
cout << "░░░░░░████▀░░███▀░░░░░░▀███░░▀██▀░░░░░░\n";
cout << "░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░\n";
      decisionValida = true;
    } else if (decision == 'n' || decision == 'N') {
      cout << "\nDecidiste no escanear tu iris...\n";
      cout << "¡De repente, el veterinario aparece desde las sombras y te atrapa!\n";
      cout << "\nQuedaste atrapadx en la casa.\n";
    cout << "███████████████████████████████████\n";
    cout << "████████████ GAME OVER ████████████\n";
    cout << "███████████████████████████████████\n";
    cout << "█████████████▒▒▒▒▒▒▒▒▒█████████████\n";
    cout << "█████████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█████████\n";
    cout << "███████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒███████\n";
    cout << "██████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒██████\n";
    cout << "█████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█████\n";
    cout << "█████▒▒▒▒█▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█▒▒▒▒█████\n";
    cout << "████▒▒▒▒███▒▒▒▒▒▒▒▒▒▒▒▒▒███▒▒▒▒████\n";
    cout << "███▒▒▒▒██████▒▒▒▒▒▒▒▒▒██████▒▒▒▒███\n";
    cout << "███▒▒▒███▐▀███▒▒▒▒▒▒▒███▀▌███▒▒▒███\n";
    cout << "███▒▒▒██▄▐▌▄███▒▒▒▒▒███▄▐▌▄██▒▒▒███\n";
    cout << "███▒▒▒▒██▌███▒▒▒█▒█▒▒▒███▐██▒▒▒▒███\n";
    cout << "██▒▒▒▒▒▒███▒▒▒▒██▒██▒▒▒▒███▒▒▒▒▒▒██\n";
    cout << "█▒▒▒▒▒▒▒▒█▒▒▒▒██▒▒▒██▒▒▒▒█▒▒▒▒▒▒▒▒█\n";
    cout << "█▒▒▒▒▒▒▒▒▒▒▒▒▒█▒▒▒▒▒█▒▒▒▒▒▒▒▒▒▒▒▒▒█\n";
    cout << "█▒▒▒▒█▒▒█▒▒▒▒██▒▒▒▒▒██▒▒▒▒█▒▒█▒▒▒▒█\n";
    cout << "██▒▒▒█▒▒█▒▒▒▒█▒██▒██▒█▒▒▒▒█▒▒█▒▒▒██\n";
    cout << "███▒█▒▒█▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒█▒▒█▒███\n";
    cout << "█████▒▒█▒▒▒▐███████████▌▒▒▒█▒▒█████\n";
    cout << "███████▒▒▒▐█▀██▀███▀██▀█▌▒▒▒███████\n";
    cout << "███████▒▒▒▒█▐██▐███▌██▌█▒▒▒▒███████\n";
    cout << "███████▒▒▒▒▒▐▒▒▐▒▒▒▌▒▒▌▒▒▒▒▒███████\n";
    cout << "████████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒████████\n";
    cout << "████████▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒████████\n";
    cout << "█████████▒▒█▒█▒▒▒█▒▒▒█▒█▒▒█████████\n";
    cout << "█████████▒██▒█▒▒▒█▒▒▒█▒██▒█████████\n";
    cout << "██████████████▒▒███▒▒██████████████\n";
    cout << "██████████████▒█████▒██████████████\n";
    cout << "███████████████████████████████████\n";
    cout << "███████████████████████████████████\n";
      decisionValida = true;
    } else {
      cout << "\nRespuesta inválida. Por favor ingresá 's' o 'n'.\n";
    }
  }
}
