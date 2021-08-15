Laboratorio 1: Crear  y  simular un inversor
######################################################

En este laboratorio se crearán inversores de distintos tamaños y se realizaran simulaciones para comparar su comportamiento

Objetivos
*********
*  Analizar la curva de VI VRS VO para un “inversor” para distintos radios :math:`{𝛽_p}/{𝛽_n}`
*  Simular el tiempo de ascenso y caída para los inversor
*  Analizar el consumo de potencia de un inversor

Procedimiento
*************

Layout y esquemático de los inversores
======================================

#.  Cree  el  esquemático  y  el  ícono  para  un  inversor    con  las  siguientes  dimensiones :math:`W_p = 20𝜆` y :math:`W_n = 10𝜆`.   Asegúrese   de   exportar   las   entradas   y   salidas.   En TutorialVLSILab se  explica  con  detalle  los  pasos  a  seguir  para  crear  una  celda refiérase a este para la creación del primer inversor, un nombre representativo para este inversor puede ser Inv_20_10.


    .. figure:: ../img/Lab1_1.png
        :name: lab1_1
        :scale: 50 %
        :align: center

        Esquemático del inversor

#.  Dibuje el layout para esta celda. Para este laboratorio :math:`V_{cc}`  y :math:`V_{ss}` deberán correr de forma  horizontal  en  la  parte  superior  e  inferior  de  la  celda  en    metal  1,    el  espacio entre :math:`V_{cc}`  y :math:`V_{ss}` será de 80 λ de centro a centro. Los transistores nmos ocuparan la parte  inferior  de  la  celda  y  los  pmos  la  parte  superior;  las  entradas  y  salidas  se conectaran por medio de contactos de metal 2, aparte de esto las ningún metal2 o 3 deberá  ser  utilizado  dentro  de  las  celdas.  Asegúrese  de  establecer  el  modelo  de Spice para los transistores.

    .. figure:: ../img/Lab1_2.png
        :name: lab1_2
        :scale: 50 %
        :align: center

        Layout para del inversor

#.  Use la herramienta DRC para verificar que el layout cumple con las reglas de diseño

#.  Verifique que el layout y el esquemático sean equivalentes por medio de NCC. Puede ver la celda en 3D para tener un mejor entendimiento de la interacción entre las distintas capas:

    .. figure:: ../img/Lab1_3.png
        :name: lab1_3
        :scale: 50 %
        :align: center

        Vista en 3D del inversor

#.  Ahora cree otros dos inversores (las tres vistas) para dos grupos de dimensiones: :math:`W_p = 10𝜆`, :math:`W_n = 10𝜆` y :math:`W_p = 15𝜆`, :math:`W_n = 5𝜆`. El tamaño de la celda se debe mantener. Para hacer esto más rápido de click derecho  sobre la celda Inv_20_10 seleccione “Duplicate cells in group” cambie el nombre para el grupo y modifique esta nueva celda.

    .. figure:: ../img/Lab1_4.png
        :name: lab1_4
        :scale: 20 %
        :align: center

        Menu de duplicación de celdas

    .. figure:: ../img/Lab1_5.png
        :name: lab1_5
        :scale: 50 %
        :align: center
    
        Layout para las distintas versiones del inversor

#.  Use las herramientas DRC y NCC para las dos nuevas celdas que creó
#.  El largo de la celda es límitado,  debe ser de 80 λ desde el centro de gnd al de vdd, pero la celda puede crecer en ancho tanto como se quiera. Teniendo esto en cuenta  cree un inversor de tamaño :math:`W_p = 40𝜆` y :math:`W_n = 20𝜆`

Simulación 1: curva de transición del inversor
==============================================

#.  Haga una copia de los layout para realizar una simulación

#.  Prepare la simulación, puede apoyarse en el tutorial

#.  Realice un análisis DC  donde se determine el valor de Vout para un valor dado de Vin, realice un grafico de :math:`V_{out}` vs :math:`V_{in}` para cada uno de los transistores

    .. figure:: ../img/Lab1_6.png
        :name: lab1_6
        :scale: 50 %
        :align: center

        VTC del inversor

#.  Determine los márgenes de ruido para cada uno de estos inversores

#.  Identifique   las   regiones   de   operación.   Los   voltajes   de   umbral   los   puede encontrar en el archivo Spice.txt
    
    Recuerde  que  el  punto  medio  de  voltaje :math:`V_m` está  definido  como  el  punto  donde  la curva característica del inversor interseca la línea de ganancia unitaria es decir :math:`V_m` es  el  punto  donde  :math:`V_{out}`  es  igual  a  :math:`V_{in}`.  Un  valor  de :math:`V_{in} = V_m` no  representa  una cantidad booleana, pero, para :math:`V_{in}` menor a :math:`V_m` indica que salida es más cercana a un cero lógico.
    
    Un  inversor  simétrico  es  aquel  que  tiene    un  rango  de  voltajes  de  entrada,  que permite  que la  tensión  de  salida  tenga  un rango 0  y  1  de  igual  tamaño.  Esto  se logra cuando:
    
    .. math::
        V_m = 12 V_{dd}

#.  Encuentre :math:`V_m` para  los  distintos  transistores,  compare  el  valor  obtenido  con  el valor teórico, deber encontrar una expresión para :math:`V_m` en términos de los voltajes de umbral de los transistores y de β

#.  Analice   como   afecta   el   dimensionamiento   de   los   transistores   la   curva característica  del  inversor  encuentre  la  relación  para :math:`{𝛽_p}/{𝛽_n}` los  transistores  que simuló


Simulación 2: potencia
======================
#.  Para los siguientes cálculos considere el inversor simétrico de dimensiones :math:`W_p = 20𝜆` y :math:`W_n = 10𝜆` 

#.  De   la   simulación   anterior,   visualice   la   corriente   del   inversor   durante   la transición,  observe  que  la  corriente  alcanza  un  pico  en   :math:`V_m`,  que  implicaciones tiene esto en consumo de potencia?

#.  La  potencia  dinámica  :math:`P_{dyn}` deriva  del  hecho  de  que  cuando  hay  una  transición de  se crea un camino de Vdd  y Gnd que carga  o descarga :math:`C_{out}`. Considere que la señal  de  entrada  es  una  onda  cuadrada  con  un  periodo  de  10ns,  y  que  la  carga para el inversor de de 4FO. Con estos datos calcule :math:`P_{dyn}`.


Simulación 3: tiempo de ascenso y caída
=======================================
#.  Las  compuertas  lógicas    introducen  un  tiempo  de  retardo  cuanto  sus  entradas cambian,  la  señal  de  entrada  reacciona  a  la  salida,  pero  el  voltaje  de  salida  no puede  cambiar  de  forma  instantánea.  La  transición    de  la  salida  de 1  a  0  es  el retardo  de  caída  y  de  0  a  1  el  de  ascenso.  Estos  tiempos  se  pueden  calcular analizando las transiciones de los circuitos

#.  Realice una simulación con una carga de 4FO, en el los archivos de Spice puede ver  cuánto  es  la  capacitancia  de  entrada  para  cada  uno  para  cada  uno  de  los inversores  que  dibujó.  El  tiempo  de  ascenso  y  de    caída  se  definirán  como  el tiempo de la compuerta de pasar del 10% al 90% de su valor final


    .. figure:: ../img/Lab1_7.png
        :name: lab1_7
        :scale: 50 %
        :align: center

        Tiempos de ascenso y caída

#.  Compare los tiempos ascenso y caída para los distintos inversores que dibujó

#.  Ahora  manteniendo  la  misma  carga,  varíe  la  forma  de  la  señal  de  entrada, cambiando  el  slope,  algo  similar  a  lo  que  se  muestra  a  continuación,  escoja  5 valores para este slope  y simule para cada inversor, compare. Como afecta esta variación en la salida la velocidad de respuesta del inversor

    .. figure:: ../img/Lab1_8.png
        :name: lab1_8
        :scale: 50 %
        :align: center

        Slope de entrada

Simulación 4: ruido
===================
#.  Para analizar la inmunidad al ruido del inversor genere señales a la entrada que le  permitan  determinar    como  se  ve  afectado  el  valor  de  la  salida  por  el  ruido. Determine  qué  valor  de  voltaje  en  la  entrada  logra  distorsionar  la  salida. Itere cuantas veces sea necesario

#.  ¿Cómo  se  ven  afectados  estos  valores  por  el  dimensionamiento  del  transistor? Qué nivel lógico se está beneficiado, en términos de inmunidad al ruido, con el dimensionamiento de los transistores.Figura 6.13. Laboratorio 1: Simulación de Ruido

    .. figure:: ../img/Lab1_9.png
        :name: lab1_9
        :scale: 50 %
        :align: center

        Simulación de ruido

