# Proyecto: Sistema en línea de producción - Botes de mermelada

## Definición del proyecto Sprint Planning 27/10/2023

El objetivo principal del proyecto es automatizar la línea de produccion para el llenado de botes de mermeladas, colocar su tapa y realizar el empaquetado de los mismos. A través de una cinta transportadora los botes vacios llegan a la estación de llenado, luego son transportados a la estacion de tapado, donde se coloca la tapa a los botes. Finalmente son transportados a la estacion de empaquetado, donde se embalan en cajas de 6 unidades.

## Desarrollo del Proyecto:

- Entorno de Modelado y Simulacion: se utiliza el softare en version free de CADe_SIMU y PC_SIMU, el cual permite modelar y simular el comportamiento de un sistema de control.

- Definición de componentes:

  - Pilotos LED:
  - Pulsadores: Ter, P, PG, PM
  - Motores: M1 (carga de tanque), M2 (cinta transportadora para llenado y tapado), M3 (cinta transportadora para empaquetado)
  - Válvulas: V1e (entrada de mermelada), V1s (salida de mermelada)
  - Sensores de Nivel: B2 (nivel mínimo), B1 (nivel máximo), B3 (detener para llenado), B5 (detener para tapado), B6 (posición de tapa)
  - Actuadores neumáticos: B(coloca tapa),
  - Contador: C1 (contador de botes para empaquetado).
  - Cinta transportadora: para llenado y tapado, para empaquetado.

- Descripcion de funcionamiento:

- Etapa de preparación:
  Con la puesta en marcha se enciendo motor M1, abre valvula V1e, se llena el tanque de mermelada hasta que el sensor B2 detecta el nivel máximo, se cierra la válvula V1e y se apaga el motor M1.

- Etapa de llenado:
  Se enciende el motor M2 de cinta transportadora, se posiciona el bote vacio en la estación de llenado (detinda la cinta por sensor B3), se abre la válvula V1s y se llena hasta uan cantidad programada, se cierra la válvula V1s y B3 permite el paso a la siguiente etapa.

- Etapa de tapado:
  Se posiciona el bote lleno en la estación de tapado (detenida la cinta por sensor B5), se activa el actuador neumático B(coloca tapa), se desactiva el actuador neumático B, y B5 permite el paso a la siguiente etapa (activa cinta).
- Etapa de empaquetado:
  Se enciende el motor M3 de cinta transportadora de empaquetado, con un contador se cuentan 6
  (un valor configurable) botes y se detiene la cinta transportadora hasta el completado de la caja.

- Etapa final:
  La caja completa es retirada de la cinta transportadora y se coloca una nueva caja vacia para continuar el proceso.
