# LineFollower
Seguidor de linea básico


### Objetivo:

Aprender a construir un seguidor de línea con el uso de componentes electrónicos como motores y sensores
infrarrojos, para seguir una línea de color blanco o negra.

### Material

* 2 LEDs (Del color de tu elección)
* 5 Resistencias de 220 ohms, 330 ohms, 10 k ohms.
* Cable Dupont (Macho-Hembra, Macho-Macho)
* Protoboard (Tablilla para pruebas de circuitos electrónicos)
* 2 QRD1114 ó TCRT500 (Sensores Infrarrojos)
* 1 CD4093BE (Circuito Integrado)
* 2 TIP120 (Transistor Darlington)
* 2 Baterías Recargables de 3.7 v al mismo amperaje (las de celular que no uses con carga) o batería de 9V con su
respectivo conector 
* 1 LM7805 (Regulador de voltaje) 
* 2 Motorreductores relación 1:200 (los ubicarás porque son de color amarillo) 
* 2 Llantas para tus motorreductores. 
* 2 m de Cable AWG No. 22 
* Rueda loca 
* Base para el circuiuto de sensores, control y potencia 20x30cm

### Procedimiento

1. La prueba del seguidor se puede dividir en tres partes: sensores, control y potencia (como se muestra en la imagen del circuito 1), en donde, el orden no afecta ya que llegaremos al mismo resultado.

Previo al armado del sensor, realizaremos nuestra fuente, en donde, regularemos el voltaje de 7.4 v (las dos baterías
conectadas en serie) a 5v por medio de un regulador de voltaje llamado LM7805, el circuito es el siguiente:

**CIRCUITO 1**

![Circuito 1](https://github.com/HackrobotsMX/LineFollower/blob/master/circuito1.PNG)

**Esquema del circuito 1**

![Esquema 1](https://github.com/HackrobotsMX/LineFollower/blob/master/esquema1.PNG)


#### Nota: Las baterías en serie se conectan de la siguiente manera:

![Circuito 2](https://github.com/HackrobotsMX/LineFollower/blob/master/circuito2.PNG)

**Esquema de conexión de baterías**

![Esquema 2](https://github.com/HackrobotsMX/LineFollower/blob/master/esquema2.PNG)


Se dice que es una conexión en serie de baterías porque se conecta un positivo de una batería con un negativo de otra
batería, esto sirve para aumentar el voltaje. Recuerda **no juntar las terminales libres**, porque podrías ocasionar un corto.
Si usas una batería de 9V alcalina, solo debes conectar el positivo al pin de entrada del regulador y el negativo con el pin
que es GND (tierra, masa o negativo), como se muestra a continuación:

![Circuito 3](https://github.com/HackrobotsMX/LineFollower/blob/master/circuito3.PNG)


El regulador LM7805 soporta una tensión o voltaje de entrada de hasta 25V y una mínima de 7V, es decir, para tener los
5V de salida, debemos estar alimentándolo de los 7V hasta los 25V, esto lo sabemos por la hoja de datos (datasheet), y
lo notamos en el parámetro Vi (Voltage input – voltaje de entrada). Esto lo observamos en la siguiente tabla donde lo
vemos para nuestro regulador 7805.

![Tabla de voltajes de entrada](https://github.com/HackrobotsMX/LineFollower/blob/master/TablaVI.PNG)


2. Como se mencionó en el paso 1, empezaremos por la etapa de los sensores, los cuales se encargarán de decirnos
si hay detección de luz infrarroja o no, por medio de un receptor que tienen los sensores (QRD1114 ó TCRT5000). En las
siguientes imágenes se muestra como identificar físicamente el ánodo y cátodo del infrarrojo asi como el emisor y
colector del receptor infrarrojo.

![Sensores](https://github.com/HackrobotsMX/LineFollower/blob/master/sensorinfrarrojo.png)

Sensor TCRT5000 (Izq.) y Sensor QRD1114 (Der.)

Realizaremos la prueba de cada uno de ellos (tú elige solo uno) con el encendido y apagado de LED cuando se detecte la
luz infrarroja. Cabe mencionar que existen dos configuraciones para la detección de la luz infrarroja, nosotros utilizaremos
la de colector por que deseamos ir por la línea negra, esta detección nos sirve para indicar si mandaremos un encendido
o apagado de LED. De igual manera te compartimos el esquema para hacerlo para línea blanca.

**Configuración por colector (línea negra)**

![lineaNegra](https://github.com/HackrobotsMX/LineFollower/blob/master/confColector.PNG)


**Configuración por emisor (línea blanca)**

![lineaBlanca](https://github.com/HackrobotsMX/LineFollower/blob/master/confEmisor.PNG)


**Circuito físico de sensores IR usando TCRT5000**

![CircuitoSensores](https://github.com/HackrobotsMX/LineFollower/blob/master/Circuito4.JPG)

Una forma de verificar que nuestro sensor infrarrojo funciona es con nuestra cámara de celular, esto es debido a que
nuestro ojo no lo percibe.

![Prueba](https://github.com/HackrobotsMX/LineFollower/blob/master/Circuito5.jpg)
