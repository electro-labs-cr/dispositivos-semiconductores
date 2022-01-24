Laboratorio 4: Crear compuertas dinámicas
#########################################

En este laboratorio se trabaja con compuertas dinámicas y lógica dominó

.. contents:: Contenidos del laboratorio
    :depth: 4

Objetivos
*********
*  Comprender el funcionamiento de las compuertas dinámicas y la lógica domino
*  Reconocer las ventajas y desventajas de las compuertas dinámicas en relación a las compuertas estáticas

Procedimiento
*************

..  note::
    Todas las celdas que construya deberán tener las siguientes características: Los transistores NMOS ocuparan la parte inferior de la celda y los PMOS la parte superior; las entradas y salidas se conectaran por medio de contactos de metal 2, aparte de esto ningún metal2 o 3 deberá ser utilizado dentro de las celdas

#.  Crear una  compuerta dinámica NAND2. Crear tanto la vista de layout como la de icono y esquemático

    .. list-table:: Dimensiones de la compuerta dinámica
        :header-rows: 1
        :align: center

        * - PMOS
          - NMOS
        * - 5𝞴
          - 10𝞴

    .. figure:: ../img/Lab4_1.png
        :name: lab4_1
        :scale: 40 %
        :align: center
  
        Layout de la compuerta dinámica


Creación y simulación de compuertas dinámicas
=============================================

#.  Simule  la  compuerta,  durante  la  etapa  de  precarga  y  evaluación,  y  verifique    su correcto funcionamiento

    .. figure:: ../img/Lab4_2.png
        :name: lab4_2
        :scale: 40 %
        :align: center

        Etapa de precarga y evaluación

#.  Que  sucede  si  durante  la  etapa  de  precarga,  las  entradas    A  y  B  tienen  un  valor lógico de 1?

#.  Cuando  no  se  puede  garantizar  que  las  entradas  sean  cero  durante  la  precarga,  se incluye un transistor extra al fondo de  la “Pila” NMOS,  cuya entrada es el reloj, de esta  forma  se  evita  situaciones  de  contención  durante  la  precarga.  Agregue  este transistor a la compuerta que construyo y simúlela.Figura 6.33. Laboratorio 4: NANDdinámica con transistor de pie5.Según la teoría, la salida de una compuerta, dinámica, no puede ser  conectada  a la entrada   de   otra   compuerta   dinámica,   si   tienen   el   mismo   reloj,   explique 

    .. figure:: ../img/Lab4_3.png
        :name: lab4_3
        :scale: 40 %
        :align: center

        Simulación de la nand dinámica con un transistor extra


#.  Según la teoría, la salida de una compuerta, dinámica, no puede ser  conectada  a la entrada   de   otra   compuerta   dinámica,   si   tienen   el   mismo   reloj,   explique detalladamente  porque  y  realice  simulaciones  que  la  comprueben.  Una  forma sencilla de simularlo es mediante inversores dinámicos en cadena

    .. figure:: ../img/Lab4_4.png
        :name: lab4_4
        :scale: 30 %
        :align: center

        Inversores dinámicos en cadena

    .. figure:: ../img/Lab4_5.png
        :name: lab4_5
        :scale: 40 %
        :align: center

        Simulación de inversores dinámicos en cadena

#.  Esto  se  soluciona  agregando  un  inversor  estático  luego  de  la compuerta  dinámica. Cree una compuerta and2 en lógica domino. Debe dimensionar los transistores para el  inversor  tomando  en  cuenta  cual  es  la  etapa  crítica  para  la  lógica  dinámica. Explique.

    .. figure:: ../img/Lab4_6.png
        :name: lab4_6
        :scale: 30 %
        :align: center

        Layout de una AND en lógica dominó

#. Conecte  dos  compuertas  dominó  and2  y  simule  su  comportamiento,  muestre  los nodos intermedios.

    .. figure:: ../img/Lab4_7.png
        :name: lab4_7
        :scale: 40 %
        :align: center

        Simulación de dos compuertas and2 en lógica dominó

#.  Si  el  nodo  dinámico  de  la  nand2  y  es  precargado  y  en  evaluación  permanece  en uno,  eventualmente  el  nodo  se  descarga,  esto  puede  ocurrir  en  nanosegundos  o milisegundos, realice una simulación donde observe este comportamiento

    .. figure:: ../img/Lab4_8.png
        :name: lab4_8
        :scale: 40 %
        :align: center

        Simulación del nodo dinámico de la compuerta nand2

#.  Investigue sobre “Keeper” como una técnica para prevenir la descarga del nodo dinámico,  ¿Que  se  debe  tener  en  cuenta  cuando  se  dimensiona  este  elemento? Explique

#.  Agregue  un“keeper ” a la compuerta nand2 y dimensiónelo de forma que el nodo dinámico  al cabo de 6ms se mantenga por encima de 4.75 V. El ciclo del “reloj” debe ser de 20 ms


Charge Sharing
==============

#.  Investigue sobre el fenómeno de Charge Sharing. En términos de la capacitancia, de los nodos, escriba una ecuación que describa el valor de tensión del nodo dinámico

#.  Utilizando  la  nand  de  2  entradas  haga  una  simulación  donde  se  presente  este fenómeno

    .. figure:: ../img/Lab4_9.png
        :name: lab4_9
        :scale: 40 %
        :align: center

        Simulación del fenóneno charge sharing

#. Investigue  sobre  formas  como  se  evita  este  fenómeno,  implemente  alguna  de  ellas en el circuito y simule nuevamente.

    .. figure:: ../img/Lab4_10.png
        :name: lab4_10
        :scale: 40 %
        :align: center

        Simulación aplicando técnicas para evitar el fenóneno charge sharing