Laboratorio 5: Celda compleja y algoritmos de placement (opcional)
##################################################################

Se crea un sumador y se explora la complejidad de los algoritmos de placement

.. contents:: Contenidos del laboratorio
    :depth: 4

Objetivos
*********
*  Construir un sumador con las compuertas construidas en los laboratorios anteriores
*  Reconocer las dificultades en términos de área, enrutamiento, dimensionamiento de celdas que conlleva construir un circuito complejo


..  note::
    Recomendaciones:

    *  Construya un diseño modular, esto facilita la construcción y encontrar errores
    *  Copie  la  topología  de  conexiones  del  esquemático  al layout  (Unrouted  arc  de Electric)
    *  Para  facilitar  su  trabajo  utilice  las  herramientas  de  enrutamiento  de  Electric, puede que necesite hacer parte del enrutamiento de forma manual


Procedimiento
*************

Construcción del sumador
========================
#.  Investigue sobre los siguientes algoritmos de “placement” Random, Force-directed  y  Mincut.  Escriba  una  descripción  de  un  párrafo  para cada  uno  de estos algoritmos

#.  Construya  el  esquemático  para  un  sumador  (ripple  carry  adder)  de  4  bits. Utilice las celdas que construyo en los laboratorios anteriores

#.  Construya  tres  versiones  de  “layout”  para  el  sumador  utilizando  los algoritmos de “placement” mencionados anteriormente. 

    .. figure:: ../img/Lab5_1.png
        :name: lab5_1
        :scale: 40 %
        :align: center

        Algoritmos de placement

#.  Ahora  conecte  los  diferentes  componentes  del    el  circuito,  puede  utilizar  el alguno de los enrutadores de Electric. Recuerde que solo se puede usar hasta Metal 3

#.  ¿Qué  dificultades  tuvo  para  construirlo?  ¿Tuvo  que  sacrificar  área  para lograr   enrutar   el   circuito? Compare  los  algoritmos  de  “placement”  y explique


Simulación del sumador
======================
#.  Simule el sumador, piense en el estimulo crítico para este. Explique porque eligió el ese estímulo

#.  Comprare el tiempo de suma para las distintas versiones del circuito.

#.  Compare  ahora  los tres  algoritmos  considerando  área,  tiempo  de  suma  y facilidad para conectar los elementos del circuito.