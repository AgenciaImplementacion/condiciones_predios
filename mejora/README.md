# Descripción del caso

![Caso mejora]()

Una construcción realizada en un terreno ajeno, eso quiere decir que el dueño de la construcción no es el mismo dueño del terreno.

# Representación LADM

Para representar este caso de acuerdo a LADM se necesitarán de las siguientes tablas del modelo (v 2.2.1)

![Diagrama Entidad Relación simplificado]()

# Flujo de almacenamiento

Para este caso se deben crear registros para dos predios, uno que tiene un interesado y un terreno asociado, y otro que tiene una construcción asociada pero no tiene terreno asociado.
(**Datos del predio con terreno**)

1. **Llenar tabla Terreno**: En esta tabla se agregan los datos relacionados con la representación espacial, tales como el área y la geometría, del polígono de terreno (verde)
2. **Llenar tabla Predio**: En esta tabla se agregan datos alfanuméricos del predio al cuál pertenece el terreno, tales como el Número Predial, FMI, etc.
3. **Llenar relación UEBAUnit vinculando Terreno con Predio**
4. **Llenar tabla COL_Interesado**: Esta tabla contiene los datos de la persona (natural o jurídica) que ejerce el derecho de Dominio sobre el predio
8. **Llenar tabla COL_FuenteAdministrativa**: Esta tabla se agrega información de los documentos que soportan el derecho de Dominio
9. **Llenar tabla COL_Derecho**: En esta tabla se vincula el Interesado con el Predio, especificando el tipo de derecho que se ejerce(para el caso un Dominio)
10. **Llenar relación rrrFuente, vinculando COL_Derecho con COL_FuenteAdministrativa**
----------------------------------------------------------------
(**Datos del predio sin terreno, pero con construcción**)

11. **LLenar tabla Construccion**: En esta tabla se agregan los datos de la construcción de la mejora, que incluye datos como avalúo y área de construcción, etc
12. **Llenar tabla unidadconstruccion**: En esta tabla se agregan los datos de la unidad de construcción de la mejora, que incluye datos tales como avalúo, número de pisos, y el id de la construcción con la cuál está relacionada.
13. **Llenar tabla predio**: En esta tabla se agregan los datos alfanuméricos del predio al cuál pertenece la construcción.
14. **Llenar relación UEBAUnit vinculando Construccion con Predio**
15. **Llenar tabla COL_Interesado**: Esta tabla se agregan los datos de la persona (natural o jurídica) que ejerce el derecho de Posesión sobre su predio
16. **Llenar tabla COL_FuenteAdministrativa**: En esta tabla se agrega la información de los documentos que soportan el derecho de Posesión
17. **Llenar tabla COL_Derecho**:En esta tabla se vincula el Interesado (dueño de la mejora) con su Predio, especificando el tipo de derecho como una Posesión
18. **Llenar relación rrrFuente, vinculando COL_Derecho con COL_FuenteAdministrativa**


# Productos

![Esquema de tablas]()
