# Telematics
<p><code>Fundamentos de Telemática</code></p>
<p>Creado por <code>GncDev</code> para explicar los fundamentos de los <code>Sistemas de comunicaciones</code> en los cursos de telemática y redes de computadores.</p>

# Practica de laboratorio 04 - Enrutamiento Dinámico RIP
# Estudiantes: Daniel Libardo Zambrano López- Lizzeth Carolina Rosero Trejo

## Objetivos 

### Objetivo General
Proporcionar el conocimiento y generar las habilidades necesarias en la configuración y gestión de dispositivos de redes.

### Objetivos Específicos:
- Conocer configuraciones básicas de enrutamiento dinámico con MikroTik. :+1:

---

## Parámetros:
Para todos los efectos:
* la letra G  de se reemplaza por el número de grupo de laboratorio.
* la letra C  de se reemplaza por el ultimo número de cédula del estudiante..


## 1. [Configurar el entorno de trabajo](#) ✔
1. Cree si no existe el repositorio llamado <code>Redes-dos</code>.
    ![Alt text](img/repo.PNG)
1. Crear una carpeta en este repositorio llamado <code>Laboratorio-cuatro</code>.
    ![Alt text](img/lab4.PNG)
1. Invite a los compañeros de grupo como colaboradores en este repositorio.
    ![Alt text](img/colab.PNG)
1. Documente cada uno de los items a continuación con capturas de pantalla y código.

>Nota: recuerde que los [parámetros](#parámetros) son validos en todo el laboratorio.

[1_2]:https://github.com/GiancarloBenavides

## 2. [Preguntas reflexivas de ambientación](#) ✔

<ol type="a">
<li>¿Como funcionan los servidores DHCP y DNS?</li>
    Servidor DHCP (Protocolo de configuración dinámica de host): El protocolo DHCP se utiliza para asignar direcciones IP de manera dinámica a dispositivos en una red. Esto es especialmente útil en redes grandes donde asignar direcciones IP manualmente sería un proceso engorroso, funciona: de esta manera: 
    Solicitud: cuando un dispositivo se encuentra en la red y está configurado para obtener una dirección IP automáticamente, envía una solicitud de "DHCP Discover" a la red
    Oferta: Los servidores DNS (Domain Name System) son fundamentales para la navegación en internet, ya que permiten traducir los nombres de dominio que utilizamos, como "www.ejemplo.com", en direcciones IP que las computadoras pueden entender.
<li>¿Que desventajas tienen las rutas estáticas frente a las dinámicas?.</li>
    Las rutas estáticas y dinámicas son dos enfoques diferentes para el rutamiento en una red de computadoras. Cada enfoque tiene sus propias ventajas y desventajas. 
    Desventajas más comunes de las rutas estáticas en comparación con las rutas dinámicas:
    Desventajas de las rutas estáticas: 
        1. Falta de Adaptabilidad: Las rutas estáticas deben configurarse manualmente en cada dispositivo de red. Esto puede ser problemático en redes grandes o en entornos donde la topología de red cambia con frecuencia. Si se agregan o eliminan dispositivos o cambian las conexiones, las rutas estáticas deben actualizarse manualmente, lo que puede llevar tiempo y aumentar la posibilidad de errores. 
        2.Eneficiente para Redes Grandes o Completas.

<li>¿Cual es el algoritmo y la métrica que implementa RIP?.</li>
    RIP (Protocolo de información de enrutamiento) es un protocolo de enrutamiento de tipo vector de distancia que utiliza el algoritmo de Bellman-Ford como base para determinar las rutas óptimas en una red. Además del algoritmo, RIP utiliza una métrica específica para determinar la distancia o el costo de las rutas. La métrica que utiliza RIP se llama "conteo de saltos" o "hop count". Algoritmo y la métrica: RIP utiliza el algoritmo de Bellman-Ford para calcular las rutas más cortas en una red. En este algoritmo, cada enrutador mantiene una tabla de enrutamiento que contiene información sobre las redes alcanzables y el número de saltos (hops) necesarios para llegar a esas redes. Los enrutadores intercambian información de enrutamiento periódicamente con sus vecinos para actualizar sus tablas de enrutamiento. 
<li>¿Que diferencias hay entre las versiones 1 y 2 de RIP?. (Ventajas y Desventajas)</li>
    Autenticación:
    RIPv1: No tiene mecanismo
    RIPv2: Introduce la autenticación.
    Máscaras de Subred:
    RIPv1: Utiliza máscaras de
    RIPv2: Admitir máscaras
    Enrutamiento Multidifusión:
    RIPv1: Utilización
    RIPv2: Introducir
    Compatibilidad de versiones:
    RIPv1: No es compatible con R
    RIPv2: Introducir compatibilidad hacia
    Soporte para IPv6:
    RIPv1: No tiene soporte nat
    RIPv2: Se ha extendido para

<li>¿Que diferencias hay entre una IP estática, una IP dinámica y una IP reservada?.</li>
    una dirección IP estática se configura manualmente y permanece constante, una dirección IP dinámica se asigna automáticamente y puede cambiar con el tiempo, y las direcciones IP reservadas tienen usos específicos y no suelen asignarse
    IP Reservada (IP Reservada):
    •	Las direcciones IP reservadas son direcciones que están reservadas para
    •	Estas direcciones se utilizan para propósitos especiales, como para
    •	También se pueden reservar direcciones
    •	Ejemplos de direcciones IP reservadas son la dirección IP de red, la dirección de difusión y direcciones utilizadas para documentación o fines privados (como direcciones en el rango 192.168.xx para redes locales).
    Dirección IP Estática:
    •	Una dirección IP estática es una dirección IP fija y
    •	No cambia a menos que se real
    •	La administración de direcciones IP está
    Dirección IP Dinámica:
    •	Una dirección IP dinámica es una dirección IP que se asigna automáticamente a un dispositivo en la red cuando se conecta
    •	Las direcciones IP dinámicas pueden cambiar cada vez que un dispositivo se desconecta y se vuelve a conectar a la red.
    •	Es eficiente para redes grandes, ya que el servidor DHCP puede asignar direcciones IP de manera automática y controlada.


</ol>


## 5. [Configuración básica MikroTik-02](#) ✔
1. Conecte los equipos a la red eléctrica.
1. [Reinicie][3_1] los dispositivos a la configuración de fabrica.
1. Conecte la ultima interfaz [RJ45][rj45] del router al PC de configuración.
1. [Acceder][3_2] al dispositivo por el puerto 8291 via Winbox.
1. Cambiar el nombre del dispositivo para [identificarlo][3_3] como <code>R2</code>.
    ![Alt text](img/nombre.PNG)

1. Etiquetar las [interfaces][3_4] a utilizar (2 WAN y una LAN).
1. Conecte las interfaces [Ethernet][3_5] etiquetadas a los equipos vecinos.
1. Agregar un [bridge][3_6] y sus interfaces para la red LAN.
    ![Alt text](img/14.PNG)
1. Agregar el direccionamiento para las dos redes externas WAN y la red interna LAN.
    1. Agregar la [dirección][5_1] de la interfaz externa que conecta con R1 en el segmento IP 10.11.1.0/24.
    1. Agregar la [dirección][5_1] de la interfaz externa que conecta con R3 en el segmento IP 10.22.1.0/24.
    1. Agregar la [dirección][5_1] del bridge (interna) con una IP 192.168.22.1 privada, clase C.
1. Agregar un [Pool][5_2] en el segmento de la LAN que asigne direcciones entre 192.168.22.100-192.168.22.200.
    ![Alt text](img/pool.PNG)
1. Agregar un servidor [DHCP][5_3] y la información de puerta de enlace y DNS que enviara a los PC conectados a la LAN.
    ![Alt text](img/DHCP.PNG)
1. Convertir a [estático][5_4] el arrendamiento DHCP para la MAC del PC de configuración. 
1. Cambiar la ip estática del pc de configuración a 192.168.22.10.
1. Crear una regla [source NAT][5_5] en el cortafuegos para enmascarar la ip de origen.
    ![Alt text](img/14.PNG)
1. Agregar la [ruta por defecto][5_6] 0.0.0.0/0.
    ![Alt text](img/15.PNG)

## 6. [Configurar enrutamiento MikroTik-02](#) ✔
1. Agregar [Rip][8_1] a las interfaces conectadas a los router vecinos.
    ![Alt text](img/RIP1.PNG)

    ![Alt text](img/RIP2.PNG)
1. Publicar las [redes][8_2] que las interfaces rip deben compartir para que los tres router conozcan la ruta a los otros dos y a sus redes LAN.
    ![Alt text](img/2.PNG)
1. Realizar pruebas de diagnostico [PING][8_3] y [TRACEROUTE][8_4] desde el router a los otros router.   
1. Realizar pruebas de diagnostico [PING][ping] y [TRACERTE][tracert] desde un computador conectado via UTP a los otros router.
1. Realizar un [backup][8_5] de la configuración del equipo.
    ![Alt text](img/back1.PNG)

    ![Alt text](img/back1.PNG)


## 9. [Diagrama de Red](#) ✔
- Realice un diagrama topológico de cada uno de los casos de estudio.
- Incluya todos los detalles de la red de area local a la que se encuentra conectado.
- Incluya los saltos conocidos incluyendo el equipo de borde de su ISP.

![Arquitectura](../img/lab-04.svg "Arquitectura laboratorio 04")

## 10. [Preguntas de conocimiento](#) ✔
1. ¿Por qué no se puede llegar a 10.10.1.100 desde R3 y 10.33.1.1 desde R1? 
1. ¿Que se necesitaría para lograr llegar a 10.10.1.100 desde R2?
1. ¿Que se necesitaría para lograr llegar a 10.33.1.1 desde todos los routers?
1. ¿Permite el protocolo RIP compartir rutas entre diferentes Sistemas Autónomos? (Justifique)

[psk]:https://es.wikipedia.org/wiki/Pre-shared_key
[dhcp]:https://es.wikipedia.org/wiki/Protocolo_de_configuraci%C3%B3n_din%C3%A1mica_de_host
[wlan]:https://es.wikipedia.org/wiki/Red_de_%C3%A1rea_local_inal%C3%A1mbrica

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
[5_4]:https://wiki.mikrotik.com/wiki/Manual:IP/DHCP_Server#Menu_specific_commands_2
[5_5]:https://wiki.mikrotik.com/wiki/Manual:IP/Firewall/NAT#Source_NAT
[5_6]:https://wiki.mikrotik.com/wiki/Manual:IP/Route#Default_route

[8_1]:https://wiki.mikrotik.com/wiki/Manual:Routing/RIP#Interface
[8_2]:https://wiki.mikrotik.com/wiki/Manual:Routing/RIP#Network
[8_3]:https://wiki.mikrotik.com/wiki/Manual:Tools/Ping
[8_4]:https://wiki.mikrotik.com/wiki/Manual:Troubleshooting_tools
[8_5]:https://wiki.mikrotik.com/wiki/Manual:System/Backup

---
## Mas Recursos
- [Wiki Mikrotik](https://wiki.mikrotik.com/wiki/Main_Page) (MikroTik - Wiki)
- [Video-Curso Mikrotik](https://www.youtube.com/watch?v=SLAPzl-LSc0&list=PLf0g2cV4iCkH19_UhaVt0vDn1f9ObumjF) (Wiki)
- [Encaminamiento](https://es.wikipedia.org/wiki/Encaminamiento) (Wikipedia)
- [RIP](https://es.wikipedia.org/wiki/Routing_Information_Protocol) (Wikipedia)
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