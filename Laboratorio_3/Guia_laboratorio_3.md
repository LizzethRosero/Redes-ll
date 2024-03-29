# Telematics
<p><code>Fundamentos de Telemática</code></p>
<p>Creado por <code>GncDev</code> para explicar los fundamentos de los <code>Sistemas de comunicaciones</code> en los cursos de telemática y redes de computadores.</p>

# Practica de laboratorio 03 - Enrutamiento estático
# Estudiantes: Daniel Libardo Zambrano López- Lizzeth Carolina Rosero Trejo

## Objetivos 

### Objetivo General
Proporcionar el conocimiento y generar las habilidades necesarias en la configuración y gestión de dispositivos de redes.

### Objetivos Específicos:
- Conocer configuraciones básicas de enrutamiento estático con MikroTik. :+1:

---

## Parámetros:
Para todos los efectos:
* la letra G  de se reemplaza por el número de grupo de laboratorio.
* la letra C  de se reemplaza por el ultimo número de cédula del estudiante..


## 1. [Configurar el entorno de trabajo](#) ✔
1. Cree si no existe el repositorio llamado <code>Redes-dos</code>.
    ![Alt text](img/repo.PNG)
1. Crear una carpeta en este repositorio llamado <code>Laboratorio-tres</code>.
    ![Alt text](img/lab3.PNG)
1. Invite a los compañeros de grupo como colaboradores en este repositorio.
    ![Alt text](img/colab.PNG)
1. Documente cada uno de los items a continuación con capturas de pantalla y código .

>Nota: recuerde que los [parámetros](#parámetros) son validos en todo el laboratorio.

## 2. [Preguntas reflexivas de ambientación](#) ✔

<ol type="a">
<li>¿Que es y como se configura la ruta por defecto?</li>
    Rta:La ruta por defecto se refiere a la dirección de red que un sistema operativo utiliza para enviar paquetes de datos a una ubicación fuera de su propia red local. Cuando un dispositivo, como una computadora, necesita enviar datos a una dirección IP que no está en su propia red local, utilice una puerta de enlace predeterminada o "ruta por defecto" para dirigir los paquetes hacia el enrutador que se encargará de dirigirlos hacia su Destino final.
    CONFUGURACION:
<li>¿Que es la distancia administrativa?.</li>
     Rta:se refiere a un concepto utilizado en enrutamiento para determinar la confiabilidad de una fuente de información sobre rutas en un enrutador o dispositivo de red. La distancia administrativa se utiliza para tomar decisiones sobre cuál es la mejor ruta cuando hay múltiples rutas disponibles para llegar a un destino.
     Cada protocolo de enrutamiento tiene una distancia administrativa asociada, que es un valor numérico predefinido que indica cuán confiable se considera el protocolo en términos de proporcionar información precisa sobre las rutas. Cuando un enrutador recibe información de enrutamiento de diferentes protocolos, utilice la distancia administrativa para determinar qué información de enrutamiento debe priorizarse en caso de que haya rutas conflictivas hacia un destino.
<li>¿Que es una red directamente conectada y cual es su distancia administrativa?.</li>
    Rta:Una red directamente conectada es una red o un conjunto de dispositivos que están conectados básicamente a un mismo segmento de red, de manera que pueden comunicarse entre sí sin necesidad de pasar a través de ningún dispositivo de enrutamiento adicional.
    La distancia administrativa para una red directamente conectada es 0. Esto significa que, en términos de prioridad de enrutamiento, las rutas directamente conectadas son consideradas las más confiables y preferidas. Cuando un enrutador tiene una interfaz conectada directamente a una red, considera esa ruta como la mejor opción para alcanzar los dispositivos en esa red debido a su distancia administrativa más baja.

    Por ejemplo, si tienes un enrutador con una interfaz conectada directamente a la red 192.168.1.0/24, esa ruta se considera la ruta preferida para llegar a todos los dispositivos en esa red. Si un dispositivo en esa red desea enviar datos a otra red, el router utilizará la ruta directamente conectada siempre que sea posible debido a su distancia administrativa de 0.
<li>¿Que es una ruta estática?.</li>
    Rta: Una ruta estática es una entrada de enrutamiento que se configura manualmente en un dispositivo de red, como un enrutador o un servidor, por un administrador de red. En lugar de utilizar protocolos de enrutamiento dinámico que intercambian información automáticamente entre dispositivos para determinar las rutas más eficientes, las rutas estáticas se configuran de manera estática y no cambian a menos que se modifiquen manualmente.
<li>¿Que es una ruta dinámica?.</li>
    Rta: Una ruta dinámica es una entrada de enrutamiento que se establece y actualiza automáticamente en un dispositivo de red, como un enrutador, utilizando protocolos de enrutamiento dinámico. Estos protocolos permiten a los dispositivos intercambiar información de enrutamiento entre sí para determinar las rutas más eficientes y actualizadas en una red en constante cambio.

    Los protocolos de enrutamiento dinámico permiten que los routers compartan información sobre la topología de la red y las rutas disponibles. Estos enrutadores intercambian mensajes de enrutamiento para informarse mutuamente sobre las redes a las que pueden llegar y las métricas asociadas con esas rutas, que pueden incluir el costo o la distancia estimada para alcanzar una determinada red. A medida que cambian las condiciones de la red, como enlaces que se caen o se restablecen, los routers ajustan automáticamente sus tablas de enrutamiento en función de la información actualizada.
</ol>


## 5. [Configuración básica MikroTik-02](#) ✔
1. Conecte los equipos a la red eléctrica.
1. [Reinicie][3_1] los dispositivos a la configuración de fabrica.
1. Conecte la ultima interfaz [RJ45][rj45] del router al PC de configuración.
1. [Acceder][3_2] al dispositivo por el puerto 8291 via Winbox.
1. Cambiar el nombre del dispositivo para [identificarlo][3_3] como <code>R2</code>.

    ![nombre router](img/nombre.PNG)</li>
        Figura 1. 

1. Etiquetar las [interfaces][3_4] a utilizar (2 WAN y una LAN).
1. Conecte las interfaces [Ethernet][3_5] etiquetadas a los equipos vecinos.
1. Agregar un [bridge][3_6] y sus interfaces para la red LAN.

    ![nombre router](img/7.1.PNG)</li>
        Figura .
1. Agregar el direccionamiento para las dos redes externas WAN y la red interna LAN.
    1. Agregar la [dirección][5_1] de la interfaz externa que conecta con R1 en el segmento IP 10.11.1.0/24.
    1. Agregar la [dirección][5_1] de la interfaz externa que conecta con R3 en el segmento IP 10.22.1.0/24.
    1. Agregar la [dirección][5_1] del bridge (interna) con una IP 192.168.1.1 privada, clase C.
1. Agregar un [Pool][5_2] en el segmento de la LAN que asigne direcciones entre 192.168.1.100-192.168.1.200.

    ![nombre router](img/pool.PNG)</li>
        Figura .
1. Agregar un servidor [DHCP][5_3] y la información de puerta de enlace y DNS que enviara a los PC conectados a la LAN. 
1. Agregar la [ruta por defecto][5_4] 0.0.0.0/0.

## 6. [Configurar enrutamiento MikroTik-02](#) ✔
1. Agregar las [rutas estáticas][8_1] necesarias para que los tres router conozcan la ruta a los otros dos.

     ![nombre router](img/Punto6.PNG)</li>
        Figura .
1. Realizar pruebas de diagnostico [PING][8_2] y [TRACEROUTE][8_3] desde el router a los otros router.

    ![nombre router](img/ping%20r1.PNG)</li>
        Figura .

     ![nombre router](img/pingr3.PNG)</li>
        Figura .   
    
1. Realizar pruebas de diagnostico [PING][ping] y [TRACERTE][tracert] desde un computador conectado via UTP a los otros router.
  ![nombre router](img/pingmaster.PNG)</li>
        Figura .

1. Realizar un [backup][8_4] de la configuración del equipo.
  ![nombre router](img/back1.PNG)</li>
        Figura .
    
    ![nombre router](img/back2.PNG)</li>
        Figura .

## 9. [Diagrama de Red](#) ✔
- Realice un diagrama topológico de cada uno de los casos de estudio.
- Incluya todos los detalles de la red de area local a la que se encuentra conectado.
- Incluya los saltos conocidos incluyendo el equipo de borde de su ISP.

![Arquitectura](img/lab-03.svg "Arquitectura laboratorio 03")

## 10. [Preguntas de conocimiento](#) ✔
1. ¿Por qué desde un router no se puede ingresar a las redes LAN de los otros router?
1. ¿Es posible lograr que los PC conectados a R1 encuentren la ruta a los PC conectados en R3? (procedimiento)
1. ¿Cual es la puerta de enlace a internet para R1?
1. ¿Cuantos saltos internos hace un computador conectado en cada una de las redes LAN a internet? (Justifique)

[rj45]:https://es.wikipedia.org/wiki/RJ-45
[ping]:https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/ping
[tracert]:https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/tracert

[3_1]:https://wiki.mikrotik.com/wiki/Manual:Reset
[3_2]:https://wiki.mikrotik.com/wiki/Manual:Winbox
[3_3]:https://wiki.mikrotik.com/wiki/Manual:System/identity
[3_4]:https://wiki.mikrotik.com/wiki/Manual:Interface
[3_5]:https://wiki.mikrotik.com/wiki/Manual:Interface/Ethernet
[3_6]:https://wiki.mikrotik.com/wiki/Manual:Interface/Bridge

[5_1]:https://wiki.mikrotik.com/wiki/Manual:IP/Address
[5_2]:https://wiki.mikrotik.com/wiki/Manual:IP/Pools
[5_3]:https://wiki.mikrotik.com/wiki/Manual:IP/DHCP_Server
[5_4]:https://wiki.mikrotik.com/wiki/Manual:IP/Route#Default_route

[8_1]:https://wiki.mikrotik.com/wiki/Manual:IP/Route
[8_2]:https://wiki.mikrotik.com/wiki/Manual:Tools/Ping
[8_3]:https://wiki.mikrotik.com/wiki/Manual:Troubleshooting_tools
[8_4]:https://wiki.mikrotik.com/wiki/Manual:System/Backup

---
## Mas Recursos
- [Wiki MikroTik](https://wiki.mikrotik.com/wiki/Main_Page) (MikroTik - Wiki)
- [Rutas estáticas en MikroTik](https://wiki.mikrotik.com/wiki/Manual:Simple_Static_Routing) (MikroTik - Wiki)
- [Video-Curso MikroTik](https://www.youtube.com/watch?v=SLAPzl-LSc0&list=PLf0g2cV4iCkH19_UhaVt0vDn1f9ObumjF) (Wiki)
- [Direccionamiento IP](https://es.wikipedia.org/wiki/Direcci%C3%B3n_IP) (Wikipedia)
- [DHCP](https://es.wikipedia.org/wiki/Protocolo_de_configuraci%C3%B3n_din%C3%A1mica_de_host) (Wikipedia)
- [Calculadora IP](https://www.calculator.net/ip-subnet-calculator.html) (Wikipedia)

---
## Evaluación y rúbrica
- Fecha máximo entrega: 05 de Mayo de 2023
- Hora de entrega: 11:59pm	
- Nota máxima: 5.0 
- Número de actividades: 10
- Valor de cada actividad: 0.5
- Ponderación: 20%
- $\color{#DD69DD}{\text{...Carpe Diem}}$