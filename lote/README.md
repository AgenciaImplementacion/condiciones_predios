# Descripción del caso

![Caso lote](https://github.com/AgenciaImplementacion/condiciones_predios/blob/master/lote/lote-Caso.png)

Un lote de terreno.

# Representación LADM

Para representar este caso de acuerdo a LADM se necesitarán de las siguientes tablas del modelo (v 2.2.1)

![Diagrama Entidad Relación simplificado](https://github.com/AgenciaImplementacion/condiciones_predios/blob/master/lote/lote-ER.png)

# Flujo de almacenamiento

1. **Llenar tabla Terreno**: En esta tabla se agregan los datos relacionados con la representación espacial, tales como el área y la geometría, del polígono de terreno (verde)
2. **Llenar tabla Predio**: En esta tabla se agregan datos alfanuméricos del predio, tales como el Número Predial, FMI, etc; eligiendo como Tipo el valor "NPH".
3. **Llenar relación UEBAUnit vinculando Terreno con Predio**
4. **Llenar tabla COL_Interesado**: Esta tabla contiene los datos de la persona (natural o jurídica) que ejerce algún derecho sobre el predio
8. **Llenar tabla COL_FuenteAdministrativa**: Esta tabla contiene la información de los documentos que soportan los diferentes derechos existentes
9. **Llenar tabla COL_Derecho**: En esta tabla se vincula el Interesado con el Predio, especificando el tipo de derecho que se ejerce(para el caso un Dominio)
10. **Llenar relación rrrFuente, vinculando COL_Derecho con COL_FuenteAdministrativa**


# Productos

![Esquema de tablas](https://github.com/AgenciaImplementacion/condiciones_predios/blob/master/lote/lote-Tablas.png)

