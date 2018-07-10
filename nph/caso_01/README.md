# Descripción del caso

![Caso 01](https://github.com/AgenciaImplementacion/condiciones_predios/blob/master/nph/caso_01/NPH%20Caso%2001.png)

Terreno con dos usos A y B. Cuatro polígonos dentro del terreno. Tres polígonos del uso A (con 2 pisos, 1 piso y 2 pisos) y un polígono del uso B (3 pisos).

# Flujo de almacenamiento

1. Llenar tabla Terreno
2. Llenar tabla Predio
3. Llenar relación UEBAUnit, vinculando Terreno con Predio.
4. Llenar tabla Construcción: 2 construcciones, 1 por cada uso. 
   + Un multipolígono de 3 partes para el uso A. 
   + Un polígono para el uso B.

5. Llenar relación UEBAUnit, vinculando Construcción con Predio.
6. Llenar tabla Unidad de Construcción, vinculando cada Unidad de Construcción a su Construcción respectiva. 

   + Para el uso A se desagrega el multipolígono de la construcción en 5 polígonos de unidades de construcción (una por piso). 
   + Para el uso B se desagrega el polígono de construcción en 3 polígonos de unidades de construcción. 
   
7. Llenar tabla Interesado.
8. Llenar tabla Fuente.
9. Llenar tabla Derecho, vinculando Interesado con Predio.
10. Llenar relación rrrFuente, vinculando Derecho con Fuente.


# Productos

(Diagrama de tablas)

[Datos en formato de transferencia de INTERLIS (XTF)](https://raw.githubusercontent.com/AgenciaImplementacion/condiciones_predios/master/nph/caso_01/nph_caso_01.xtf)
