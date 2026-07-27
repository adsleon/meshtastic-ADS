# Introducción a Meshtastic

Meshtastic es una forma práctica de montar una red de mensajería entre dispositivos sin depender de cobertura móvil, Wi‑Fi ni Internet. Funciona sobre radio LoRa, así que cada nodo puede enviar mensajes a otros nodos cercanos y, si la red está bien montada, esos mensajes pueden ir saltando de un equipo a otro hasta llegar a destino.

La idea es sencilla: con poco consumo, bastante alcance y una configuración razonable, puedes tener comunicación básica en zonas donde la conectividad tradicional falla o directamente no existe. Para empezar no hace falta complicarse; lo importante es entender qué hace Meshtastic, qué no hace y cómo se usa bien desde el primer día.

## Qué es y para qué sirve

Meshtastic es un proyecto de código abierto pensado para comunicación descentralizada. Se usa con pequeñas placas con radio LoRa, normalmente acompañadas de una antena, una batería y, en muchos casos, un móvil para configurar y leer mensajes desde la aplicación oficial.

Sirve especialmente para:

- Comunicación entre grupos en rutas, excursiones o zonas rurales.
- Redes de apoyo en escenarios sin cobertura.
- Telemetría sencilla desde sensores o equipos remotos.
- Aprender cómo funcionan las redes y la tecnología lora.

No sustituye a WhatsApp, Telegram ni a un enlace de datos convencional. Es más lento, tiene menos ancho de banda y está pensado para mensajes cortos, estado de nodos y datos pequeños.

## Cómo funciona

Meshtastic combina tres piezas: el nodo, la radio y la red.

### Nodo

Un nodo es cada dispositivo que participa en la red. Puede ser una placa con pantalla, una placa sencilla conectada a una batería o un equipo montado en una ubicación fija para dar cobertura.

### Radio LoRa

LoRa es la tecnología de radio que usa Meshtastic. Su ventaja principal es el alcance con muy poco consumo. A cambio, transmite poca información y a velocidades bajas. Eso significa que funciona bien para texto corto, coordenadas, telemetría y avisos, pero no para archivos, voz o tráfico intenso.

### Red mallada

Cada nodo puede reenviar mensajes para otros nodos si la configuración y las condiciones de radio lo permiten. Esto crea una red de tipo mesh, donde no siempre necesitas ver directamente al destino final: basta con que haya nodos intermedios bien colocados.

## Lo que necesitas para empezar

Para una primera prueba basta con esto:

- Dos o más dispositivos compatibles con Meshtastic. //En ADS tenemos, no te preocupes por ellos de momento ;)
- Un teléfono con la app de Meshtastic o un navegador para la interfaz web, según el equipo.
- Batería o alimentación estable.

Si vas a comprar hardware, revisa siempre tres cosas antes de montar nada:

1. Que el modelo sea compatible con Meshtastic.
2. Que la frecuencia de radio sea la correcta para tu región.
3. Que la antena sea la adecuada para esa banda y el conector sea el adecuado también.

## Conceptos básicos que conviene entender

Para ampliarlos, he dejado en la carpeta Documentacion-terceros varias guias que circulan por la comunidad de telegram dónde os podeis unir libremente.

### Canal

Un canal es el espacio lógico por el que se comunican los nodos. Para que dos dispositivos se vean, deben compartir la misma configuración de canal: nombre, clave y parámetros de radio.

### Nodo principal y nodos secundarios

Normalmente un usuario configura un nodo como equipo personal y otro como nodo fijo, repetidor o estación de apoyo. No todos los nodos tienen que hacer lo mismo. Tener clara la función de cada uno evita redes caóticas y mensajes duplicados.

### Reenvío

El reenvío permite que un nodo ayude a pasar mensajes a otros. Es útil para ampliar cobertura, pero si se abusa puede generar tráfico innecesario. En redes pequeñas suele bastar con pocos nodos bien situados.

### Telemetría

Meshtastic puede enviar datos como batería, temperatura, GPS o información de sensores. Esto consume más recursos que un mensaje de texto, así que conviene activarlo solo cuando aporta valor.

### Cifrado

Los mensajes de usuario pueden cifrarse para que solo los nodos autorizados puedan leerlos. Esto es importante si la red va a usarse con información sensible o si se quiere separar grupos de trabajo.

## Primer arranque

El proceso típico para dejar un nodo listo suele ser este:

1. Encender el dispositivo y comprobar que arranca correctamente.
2. Instalar la aplicación de Meshtastic en el móvil o abrir la interfaz correspondiente.
3. Emparejar el nodo por Bluetooth, USB o Wi‑Fi, según el hardware.
4. Elegir la región de radio correcta.
5. Revisar nombre del dispositivo, canal y clave de cifrado.
6. Probar un mensaje corto entre dos nodos cercanos.
7. Confirmar que la batería, la señal y la conexión se comportan como esperas.

Si estás empezando, haz la primera prueba con dos nodos juntos en la misma habitación. Así puedes distinguir enseguida si el problema es de configuración o de cobertura.

## Qué conviene configurar primero

Hay ajustes que merece la pena revisar antes de pensar en funciones avanzadas:

- Región de radio: debe coincidir con la normativa local. //Europe - 868
- Nombre del nodo: mejor si es corto y reconocible. // Más adelante hablaremos de cómo nombrarlos
- Canal compartido: usa una configuración coherente para todo el grupo.
- Potencia de transmisión: no la subas sin motivo.
- GPS: actívalo solo si el nodo realmente lo necesita.
- Intervalos de posición y telemetría: cuanto más frecuentes, más tráfico y más consumo.

Una configuración prudente suele dar mejores resultados que tocar todos los parámetros a la vez.

## Buenas prácticas de uso

Meshtastic funciona mejor cuando la red está pensada con criterio y no como una colección de nodos sueltos.

- Coloca los nodos fijos en lugares altos y despejados cuando sea posible.
- Usa antenas adecuadas y evita sitios cerrados.
- Mantén mensajes cortos y directos.
- No envíes posiciones o telemetría con más frecuencia de la necesaria.
- Documenta qué hace cada equipo fijo para que cualquiera pueda entender la red.

También ayuda tener una norma simple de uso: mensajes breves, poca repetición y nada de pruebas continuas cuando ya se ha verificado que todo está bien.

## Limitaciones reales

Meshtastic es útil, pero no hace magia. Estas son sus limitaciones más importantes:

- El ancho de banda es bajo.
- La latencia puede ser alta si la red está ocupada.
- El alcance depende mucho del terreno, la altura, la antena y los obstáculos.
- No es una red pensada para audio, vídeo ni ficheros.
- Una mala configuración puede degradar toda la red.

Entender estas limitaciones desde el principio evita frustraciones. Muchas veces el problema no es el equipo, sino esperar que haga algo para lo que no fue diseñado.

## Errores comunes al empezar

Hay algunos fallos que se repiten bastante:

- Usar la región incorrecta.
- Montar una antena sin comprobar que sea compatible.
- Cambiar demasiados parámetros al mismo tiempo.
- Esperar cobertura real sin haber probado antes la línea de vista o la altura de instalación.
- Configurar demasiados nodos retransmitiendo a la vez.
- Olvidar que el canal y la clave deben coincidir en todos los equipos del grupo.

Si algo no funciona, vuelve a lo básico: región, antena, canal y distancia entre nodos.

## Flujo recomendado para una red pequeña

Una forma sensata de arrancar es esta:

1. Preparar dos nodos compatibles y verificar que se ven en corto alcance.
2. Confirmar que ambos usan la misma región y el mismo canal.
3. Probar mensajes de texto simples.
4. Añadir un tercer nodo para comprobar si el reenvío amplía cobertura.
5. Ajustar la posición física antes de tocar parámetros avanzados.
6. Registrar qué configuración funciona y dejarla documentada.

Con ese método se aprende rápido y se evitan cambios innecesarios.

## Qué mirar cuando todo parece fallar

Si un nodo no aparece, no recibe mensajes o no reenvía como esperas, revisa en este orden:

- Alimentación y batería.
- Antena bien conectada.
- Región correcta.
- Mismo canal y misma clave.
- Distancia y obstáculos.
- Versión de firmware y compatibilidad entre nodos.

En la práctica, la mayoría de problemas de inicio salen de uno de esos puntos.

## Para seguir

Cuando ya tengas la red funcionando, los siguientes pasos naturales suelen ser:

- Montar un nodo fijo para dar cobertura a una zona concreta. Para ello necesitas ponerte en contacto con la gente de la zona. Eso en este caso se hace por Telegram en los grupos provinciales.
- Explorar telemetría básica.
- Probar integración con GPS o sensores.
- Mejorar la documentación del despliegue.
- Definir normas de uso para el grupo.

Meshtastic permite crear una red de mensajería sencilla, barata y autónoma usando radio LoRa. Para empezar bien, lo importante es tocar muchas opciones, y entender cuatro cosas: la región de radio, la antena, el canal y el papel de cada nodo en la red.

## Fin

Con esta pequeña guia Frankestein podeis seguir investigando por vuestra cuenta y en septiembre empezaremos a trabajar con hardware real para ir más allá de las palabras y hacerlo realidad.