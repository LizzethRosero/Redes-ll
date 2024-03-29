<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>

# Telematics
<p><code>Fundamentos de Telemática</code></p>
<p>Creado por <code>Giancarlo Ortiz</code> para explicar los fundamentos de los <code>Sistemas de comunicaciones</code> en los cursos de telemática y redes de computadores.</p>

# Practica de laboratorio 01
# Nombre: Lizzeth Carolina Rosero Trejo - Codigo: 217036069

## Objetivos 

### Objetivo General
Proporcionar el conocimiento y generar las habilidades necesarias en la configuración y gestión de dispositivos de redes.

### Objetivos Específicos:
- Conocer los números necesarios para configurar y caracterizar los diferentes dispositivos de red. :+1: 

---
## 1. [Configurar el entorno de trabajo](#) ✔
1. Instalar [VSCode][1_1]
2. Instalar [Git][1_2]
3. Crear una cuenta en [github][1_3]
4. Crear el repositorio en Github llamado <code>Redes-dos</code>
5. Instalar la [extension de github][1_4] para VScode
6. Agregar <code>Usuario</code> y <code>Correo</code> globalmente para Git.
7. Clonar el repositorio remoto desde VScode.

```bash
# Para agregar Usuario y Contraseña a GIT
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

[1_1]:https://code.visualstudio.com/download
[1_2]:https://git-scm.com/download/win
[1_3]:https://github.com/
[1_4]:https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github



## 2. [Preguntas de conocimiento](#) ✔

<ol type="a">
<li>¿Cual es la dirección de red y de broadcast de un host que tiene mi IP?</li>
<li>¿Cuantos clientes puede tener la sub red 172.16.0.0/22?.</li>
<li>¿Que clase y tipo de dirección es 10.10.10.0/24?.</li>
<li>¿Que información se puede inferir de la dirección 169.254.255.200/26?.</li>
<li>¿Que información se puede inferir de la dirección 169.254.255.200/26?.</li>
</ol>

¿Cual es la dirección de red y de broadcast de un host que tiene mi IP?

|Decimal||Binario|
|--|:--:|--:|
|192.168.1.10|-->|11000000.10101000.00000001.00001010|
|255.255.255.0|-->|11111111.11111111.11111111.00000000|
| |Direccion de Red||
|192.168.1.0|-->|11000000.10101000.00000001.00000000|
||Broadcast||
|192.168.1.255|-->|11000000.10101000.00000001.11111111|

¿Cuantos clientes puede tener la sub red 172.16.0.0/22?

Formula:

$$ 2^m-2 $$


||Mascara de red||
|--|:--:|--:|
|255.255.255.0|-->|11111111.11111111.11111100.00000000|

Aplicando:

$$ 2^{10}-2=1022 $$ 

Rta/ El total de direcciones IP disponibles es 1022


¿Que clase y tipo de dirección es 10.10.10.0/24?
¿Que información se puede inferir de la dirección 169.254.255.200/26?

|10.10.10.0/24| |169.254.255.200/26|
|--|:--:|--:|
|clase: IP Privada|--|Clase B|
|Tipo: Clase A|--|Tipo: Dirrección Reservadas para uso API|
| |--|Mascara: 255.255.255.192|
||--|Subred: 4|
||--|Host por subred : 62|
||--|Total de Host disponibles: 248 - dos ulimas reservadas de broadcast y red|





## 3. [Caracterización de los adaptadores](#) ✔
|Parámetro||Valor|
|--|:--:|--:|
|Número de adaptadores Físicos|-->|4|
|Número de adaptadores Virtuales|-->|0|
|Tipo de Adaptador principal|-->|Ethernernet 802.3|
|Fabricante del Adaptador principal|-->|Qualcomm Atheros Communications Inc.|
|Código MAC del fabricante|-->|E0-CA-94|
|MAC|-->|E0-CA-94-56-A7-48|

>Nota: Para obtener los parámetros de la red, usaremos los comandos [ipconfig][10], [ifconfig][8], [getmac][9].


## 4. [Caracterización de la red](#) ✔
|Parámetro|Valor|
|--|--:|
|__Subnet__|192.168.1.0/24|
|IPv4|192.168.1.10|
|Subnet Mask decimal|24|
|Subnet Mask octetos|255.255.255.0|
|Número de direcciones de Host|254|
|Rango de direcciones de Host|192.168.1.1-254|
|IP Broadcast|192.168.1.255|
|Server DHCP| 192.168.1.1|
|Server DNS|200.21.200.10|

>Nota: Para obtener los parámetros de la red, usaremos el comando [ipconfig][10] o [ifconfig][8].


## 5. [Caracterización de la puerta de enlace](#) ✔
|Parámetro|Valor|
|--|--:|
|Número de Entradas en la tabla ARP |9|
|IPv4 Gateway|192.168.1.1|
|MAC Gateway|88-de-7c-6e-d4-b0|
|ISP|Colombia Telecomunicaciones SA ESP|
|[IP Publica][5]|161.18.61.184|
|Sistema Autónomo|AS3816|


>Nota: Para obtener los parámetros de la red, usaremos el comando [arp][11] y algún servicio web/HTTP.


## 6. [Retardo de la red](#) ✔
|Servidor|IP|Tiempo promedio/ms|
|--|--|--|
|DNS Google|8.8.8.8|42ms||
|DNS Cloudflare|1.1.1.1|72ms|
|OpenDNS|208.67.222.222|103ms|
|Alternate DNS|198.101.242.72|Tiem agotado|
|DNS Quad9|9.9.9.9|47ms|
|AdGuard DNS|94.140.14.14|99ms|
|DNS Apple|17.253.144.10|168ms|
|Verizon DNS|192.16.31.63|118ms|
|IBM DNS|129.42.38.10|143ms|
|Cisco DNS|72.163.4.161| 128ms|

>Nota: Para calcular el retardo de la red, usaremos el protocolo ICMP/[ping][12] con al menos 10 paquetes.


## 7. [Capacidad del canal](#) ✔
|Servidor|Ping/ms|Down/MB|Up/MB|
|--|:--:|--:|--:|
|[speed test][1]|50|1.13|42.96|
|[Netflix][2]|37|40|150|
|[Claro][3]|39|1.7|35.5|
|[nperf][4]|44.20|7.4|28.30|

>Nota: Para calcular el retardo de la red, usaremos el protocolo HTTP via servicio WEB.


## 8. [Distancia desde el host](#) ✔
|Servidor|Ping/ms|Numero de Saltos|
|--|:--:|--:|
|google.com|18|7|
|GMail.com|19|7|
|YouTube.com|20|7|
|dns.google|18|7|
|aws.amazon.com|42|11|
|portal.azure.com|94|20|
|login.live.com|124|16|
|Facebook.com|19|7|
|c.ns.WhatsApp.net|98|13|
|claro.com.co|159|30|
|platzi.com|67|10|
|rappi.com.co|241|30|

>Nota: Para calcular el retardo de la red, usaremos el comando ICMP/[tracert][13].

## 9. [Diagrama de Red](#) ✔
- Realice un diagrama topológico de la red que le ofrece conectividad a internet.
- Incluya todos los detalles de la red de area local a la que se encuentra conectado.
- Incluya los saltos conocidos incluyendo el equipo de borde de su ISP.

![Texto alternativo](./Topologia%20de%20mi%20hogar.PNG)

 En la topologia de red de mi hogar  podemos ver un router con un módem integrado que nos permite el acceso a Internet dentro de una red. El diagrama nos muestra que tenemos conectado 3  dispositivos usando un cable de red y varios dispositivos inalámbricos como teléfonos celulares y computadoras portátiles. En la configuración de la red, se usamos un router que nos asignó nuestro proveedor de servicios de Internet.



## 10. [Preguntas de conocimiento](#) ✔
1. Cual es la dirección de red y de broadcast de un host que tiene una ip 192.168.10.10/30.
1. Cuantos equipos o.
1. Incluya los saltos conocidos incluyendo el equipo de borde de su ISP.

|Decimal||Binario|
|--|:--:|--:|
|192.168.10.10|-->|11000000.10101000.00001010.00001010|
|255.255.255.252|-->|11111111.11111111.11111111.11111100|
| |Direccion de Red||
|192.168.10.8|-->|11000000.10101000.00001010.00001000|
||Broadcast||
|192.168.10.11|-->|11000000.10101000.00001010.00001011|

1.2 Cuantos equipos ip 192.168.10.10/30

Formula:

$$ 2^m-2 $$


||Mascara||
|--|:--:|--:|
|255.255.255.252|-->|11111111.11111111.11111111.11111100|

Aplicando:

$$ 2^{2}-2=2 $$ 

Rta/ El total de direcciones IP disponibles es 2, se dice que cuando una red es /30 es uan red muy pequeña y con su mascara 255.255.255.252 es una red conocida como enlace punto a punto


[1]:https://www.speedtest.net/es
[2]:https://fast.com/es/#
[3]:http://speedtest.claro.net.co/
[4]:https://www.nperf.com/es/
[5]:https://www.cual-es-mi-ip.net/

[8]:https://man7.org/linux/man-pages/man8/ifconfig.8.html
[9]:https://learn.microsoft.com/es-es/windows-server/administration/windows-commands/getmac
[10]:https://learn.microsoft.com/es-es/windows-server/administration/windows-commands/ipconfig
[11]:https://learn.microsoft.com/es-es/windows-server/administration/windows-commands/arp
[12]:https://learn.microsoft.com/es-es/windows-server/administration/windows-commands/ping
[13]:https://learn.microsoft.com/es-es/windows-server/administration/windows-commands/tracert


---
## Mas Recursos
- [Protocolo Ipv4](https://es.wikipedia.org/wiki/IPv4) (Wikipedia)
- [Direccionamiento IP](https://es.wikipedia.org/wiki/Direcci%C3%B3n_IP) (Wikipedia)
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