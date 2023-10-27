# Proyecto: Sistema CIP

## Definición del proyecto Sprint Planning 27/10/2023

El objetivo principal del proyecto es desarrollar una lógica de control que automatice el proceso de limpieza CIP con tres tanques: soda cáustica, agua caliente y agua fría.

### Sistema CIP

CIP (Clean-In-Place): Es un método utilizado para limpiar tuberías, tanques, actuadores y otros equipos utilizados en procesos, especialmente en la industria alimentaria, sin desmontarlos.
Un sistema CIP utiliza fluidos de limpieza (como soluciones de soda cáustica) y agua para eliminar la suciedad, los residuos de alimentos y otros contaminantes de las superficies del equipo.
Esta limpieza suele seguirse de un enjuague con agua caliente y finalmente con agua fría para asegurar que no queden residuos químicos en el equipo.

## Desarrollo del Proyecto:

- Entorno de Modelado y Simulacion: se utiliza el softare en version free de CADe_SIMU y PC_SIMU, el cual permite modelar y simular el comportamiento de un sistema de control.

- Definición de componentes: - Pilotos LED: H1, H2, H3 - Pulsadores: Rt, PG, PM - Bombas: M1 (carga), M2 (envío) - Válvulas: V1e (entrada de soda cáustica),V2e (entrada de agua caliente), V3e
  (entrada de agua fría), V1s (salida de soda cáustica),V2s (salida de agua caliente), V3s
  (salida de agua fría), V4 (salida/vaciado general)
   Sensores de Nivel: B2 (nivel mínimo), B1 (nivel máximo)

- Descripcion de funcionamiento:

Fase de Soda Cáustica:

- Al presionar PM, M1 se activa y V1 se abre para llenar el tanque de soda cáustica.
- H1 se enciende en verde mientras el tanque se está llenando con soda cáustica.
- Una vez alcanzado el nivel deseado, V1 se cierra.

Fase de Agua Caliente:

- Con M1 aún en funcionamiento, V2 se abre para llenar el tanque de agua caliente.
- H2 se enciende en verde mientras el tanque se está llenando con agua caliente.
- Tras alcanzar el nivel deseado, V2 se cierra.

Fase de Agua Fría:

- M1 sigue funcionando y V3 se abre para llenar el tanque con agua fría.
- H1 y H2 se apagan, y H3 se enciende en verde durante esta fase.
- Una vez alcanzado el nivel deseado, V3 se cierra.

Selección del Tanque para CIP:

- Luego de la preparación, se activará la bomba M2 que seleccionará el tanque adecuado para comenzar con el proceso CIP en la maquinaria y procesos correspondientes. (MODICAR CON LAS VALVULAS DE SALIDA)

Vaciado y Finalización:

- V4 se abrirá para vaciar completamente los tanques si es necesario.
- Una vez vaciado, todos los pilotos se apagan indicando la finalización del proceso.

PG es una parada de emergencia. Al presionarse, todo el proceso debe detenerse inmediatamente. H3 se encenderá en rojo cuando se active la parada de emergencia.

Rt sirve para reiniciar el proceso en caso de que se haya detenido por alguna alarma o interrupción.
