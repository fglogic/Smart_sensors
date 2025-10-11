# Smart_gas_sensor
En este repositorio se aloja toda la información pertinente al desarrollo de un sistema basado en el control ambiental del monóxido de carbono con IoT  + IA

## __Introducción:__

Este proyecto se enfoca en el control ambiental previniendo que gases como el monoxido de carbono, provoquen problemas en las personas. Para esto, se utilizan sensores monóxido de carbono para así, conocer cómo cambia la concentración de gas dentro de una habitación. Estos datos entonces permiten que un controlador, permita tomar decisiones y comparaciones para luego, activar una ventilación o la apertura de una ventana. En base a esto, el sistema se puede comportar de acuerdo al siguiente diagrama en bloques:


<p align="center">
  <img src="Block_diagram.jpg" alt="Texto alternativo" width="600"/>
</p>


La figura anterior muestra al sensor de monóxido de carbono, denotado como "Sensor CO", el envia datos al Módulo ESP, el cual recolecta estos datos. Luego se observa el bloque "Referencia CO" el cual stablece cuál es el nivel de monóxido de carbono deseado y por último se observa un bloque denominado "Sensor T y H", el cual mide la temperatura y la humedad pero como variables auxiliares, es decir, como variables que pueden ayudar a tomar una mejor decisión.

Todos estos datos son enviados a la nube para poder ser almacenados. Allí en la nube, pueden ser procesados y visualizados para conocer cómo varía la concentración de CO en el ambiente donde se la mide. Por último, se observa un bloque denominado "Relay", el cual, de ser necesario, puede activar algún sistema de potencia, como por ejemplo, un ventilador.

El Módulo ESP posee conexión mediante WiFi, lo cual posibilita utilizar protocolos MQTT y HTTP, entre otros. Actualmente el Módulo utiliza MQTT para transmitir los datos sensados, por lo tanto, si se quiere acceder a estos, se lo puede hacer mediante los tópicos explicados en la siguiente sección.

Por último, con los datos recolectados, se accede a utilizar algoritmos de Inteligencia Artificial (IA), para poder realizar predicciones de comportamientos, analizar patrones y estudiar estadisticas de cómo se comportan las variables climáticas sensadas. Este procesamiento de IA o de sistemas de control, pueden actuar en la nube sin problemas.

En este sentido entonces se puede ver la aplicación de IoT + IA que se refleja en este proyecto.

## __Casos de uso:__

El sistema se encuentra sensando todo el tiempo las variables comentadas. Para acceder a estos datos, dado que se trata de una arquitectura basada en MQTT, resulta necesario obtener los tópicos pertinetes, los cuales son:

### __Tópicos__:

Monóxido de Carbono: CO

Temperatura: Temperature

Humedad: Humidity

Relay: Relay_in

De esta forma, para tomar los datos, basta con acceder a uno de estos tópicos. Luego, se pueden guardar estos datos en alguna base de datos particular, que el usuario desee.


