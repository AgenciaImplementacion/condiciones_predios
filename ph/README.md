# Descripción del caso

![Caso PH](https://github.com/AgenciaImplementacion/condiciones_predios/blob/master/ph/ph-Caso.png)

Terreno con un predio P.H. que tiene dos construcciones.
La primera construcción es una torre residencial de 3 pisos y cada piso tiene un apartamento, la segunda es un salón comunal que pertenece al P.H.

# Representación LADM

Para representar este caso de acuerdo a LADM se necesitarán de las siguientes tablas del modelo (v 2.2.1)

![Diagrama Entidad Relación simplificado](https://github.com/AgenciaImplementacion/condiciones_predios/blob/master/ph/ph-ER.png)

# Flujo de almacenamiento

1. **Llenar tabla Terreno**: En esta tabla se agregan los datos relacionados con la representación espacial de terreno, tales como el área y la geometría
2. **Llenar tabla Construccion**: Para el caso se agregan datos espaciales y alfanuméricos de las 2 construcciones. Adicionalmente se crea una construcción por cada predio privado
3. **Llenar tabla Predio**: En esta tabla se agregan datos alfanuméricos del predio matriz y de los predios privados, adicionalmente a cada predio privado es necesario asociarle el ID del predio matriz en el atributo "Copropiedad".
4. **Llenar relación UEBAUnit vinculando el Terreno con Predio Matriz**
5. **Llenar relación UEBAUnit, vinculando las Construcciones con los Predios**: En este caso se debe relacionar la construcción de la torre residencial y la construcción del salón comunal con el registro del predio matriz. Adicionalmente se debe relacionar los predios privados con sus respectivas construcciones creadas para tal fin.
6. **Llenar tabla UnidadConstrucción**: Se crean los registros de las unidades de construcción (también llamadas unidades prediales) vinculando cada Unidad de Construcción a su Construcción respectiva.  
7. **Llenar tabla COL_Interesado**: Se deben agregar los datos de las personas (naturales o jurídicas) que ejercen algún derecho sobre cada predio
8. **Llenar tabla LA_AgrupacionInteresados**: Para el caso del predio matriz se debe crear una agrupación de interesados para la copropiedad(preferiblemente con un nombre que la identifique).
9. **Llenar tabla Miembros**: En esta tabla se relaciona la agrupación de interesados creada, con los interesados que la conforman.
10. **Llenar tabla Fraccion**: En esta tabla se registran los porcentajes de participación de cada uno de los miembros de la agrupación.
11. **Llenar tabla COL_FuenteAdministrativa**: Esta tabla contiene la información de los documentos que soportan los diferentes derechos existentes
12. **Llenar tabla COL_Derecho**: En esta tabla se vincula el Interesado con el Predio, especificando el tipo de derecho que se ejerce, para el caso un Dominio por cada predio (y para el predio matriz se debe asociar a la agrupación de interesados)
13. **Llenar relación rrrFuente, vinculando COL_Derecho con COL_FuenteAdministrativa**


# Productos

![Esquema de tablas](https://github.com/AgenciaImplementacion/condiciones_predios/blob/master/ph/ph-Tablas.png)
