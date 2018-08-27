# Descripción del caso

![Caso NPH](https://github.com/AgenciaImplementacion/condiciones_predios/blob/master/nph/NPH-Caso.png)

Terreno con cuatro construcciones.
La primera construcción tiene 2 pisos, la segunda tiene 1 piso, la tercera tiene 2 pisos y la cuarta tiene 3 pisos.

En la primera construcción se define que a pesar de tener 2 pisos, estos dos pisos constituyen la misma unidad de construcción, y lo mismo ocurre con la cuarta construcción. En cambio en la segunda y tercera construcción cada piso constituye una unidad de construcción diferente.

# Representación LADM

Para representar este caso de acuerdo a LADM se necesitarán de las siguientes tablas del modelo (v 2.2.1)

![Diagrama Entidad Relación simplificado](https://github.com/AgenciaImplementacion/condiciones_predios/blob/master/nph/NPH-ER.png)

# Flujo de almacenamiento

1. **Llenar tabla Terreno**: En esta tabla se agregan los datos relacionados con la representación espacial, tales como el área y la geometría, del polígono de terreno (verde)
2. **Llenar tabla Predio**: En esta tabla se agregan datos alfanuméricos del predio, tales como el Número Predial, FMI, etc.
3. **Llenar relación UEBAUnit vinculando Terreno con Predio**
4. **Llenar tabla Construccion**: Para el caso se agregan datos de 4 construcciones, una por cada polígono. 
5. **Llenar relación UEBAUnit, vinculando Construcción con Predio**
6. **Llenar tabla UnidadConstrucción**: Se crean los registros de las unidades de construcción (también llamadas unidades prediales) vinculando cada Unidad de Construcción a su Construcción respectiva. 

   + Para el primer polígono de construcción, se desagrega en 1 polígono de unidad de construcción. 
   + Para el segundo polígono de construcción, se desagrega en 1 polígono de unidad de construcción.
   + Para el tercer polígono de construcción, se desagrega en 2 polígonos de unidad de construcción
   + Para el cuarto polígono de construcción, se desagrega en 1 polígono de unidad de construcción. 
   
7. **Llenar tabla COL_Interesado**: Esta tabla contiene los datos de la persona (natural o jurídica) que ejerce algún derecho sobre el predio
8. **Llenar tabla COL_FuenteAdministrativa**: Esta tabla contiene la información de los documentos que soportan los diferentes derechos existentes
9. **Llenar tabla COL_Derecho**: En esta tabla se vincula el Interesado con el Predio, especificando el tipo de derecho que se ejerce(para el caso un Dominio)
10. **Llenar relación rrrFuente, vinculando COL_Derecho con COL_FuenteAdministrativa**


# Productos

![Esquema de tablas](https://github.com/AgenciaImplementacion/condiciones_predios/blob/master/nph/NPH-Tablas.png)
