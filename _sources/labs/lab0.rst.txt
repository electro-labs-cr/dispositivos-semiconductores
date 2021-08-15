.. lab0_title:

Laboratorio 0: Curvas del MOSFET
################################

.. lab0_intro:

Este laboratorio es una introducción a las herramientas que se utilizarán en los distintitos laboratorios, se inicia con una guía rápida de instalación y luego se simularán transistores PMOS y NMOS.


Objetivos
*********
*  Familiarizarse con las herramientas
*  Analizar la curva de corriente :math:`I_{ds}` contra :math:`V_{ds}`, para distintos valores de :math:`V_{gs}`
*  Identificar las regiones de operación para los transistores NMOS y PMOS


Procedimiento
*************
#.  Cree una celda en vista de layout como se muestra en la :numref:`lab0_1` , deles un nombre significativo por ejemplo NMOS_IV_lay,  como  referencia  puede  consultar  el  tutorial,  use :math:`W_n = 10𝞴`

    .. figure:: ../img/Lab0_1.png
        :name: lab0_1
        :scale: 50 %
        :align: center

        Vista de layout de un transistor NMOS

#.  Establezca el modelo de Spice para el transistor.
#.  Presione la tecla F5 para verificar que no hayan errores en el layout
#.  Exporte las terminales:

    .. figure:: ../img/Lab0_2.png
        :scale: 50 %
        :align: center

        Transistor NMOS con terminales

#.  Repita para el transistor PMOS:

    .. figure:: ../img/Lab0_3.png
        :scale: 50 %
        :align: center

        Transistor PMOS con terminales

#.  Cree una simulación para los dos transistores donde para 5 valores de :math:`V_{gs}` se muestre la relación de corriente :math:`I_{ds}` vs :math:`V_{gs}`, similar a las mostradas en la :numref:`lab0_4` y la :numref:`lab0_5` 

    .. figure:: ../img/Lab0_4.png
        :name: lab0_4
        :scale: 50 %
        :align: center

        Curvas :math:`I_{ds}` vs :math:`V_{gs}` del transistor PMOS 

    .. figure:: ../img/Lab0_5.png
        :name: lab0_5
        :scale: 50 %
        :align: center

        Curvas :math:`I_{ds}` vs :math:`V_{gs}` del transistor NMOS 

#. Identifique las regiones de operación para los transistores
