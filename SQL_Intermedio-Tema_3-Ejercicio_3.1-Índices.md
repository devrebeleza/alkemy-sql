[![Alkemy Lab](https://academy.alkemy.org/images/alkemy-logo.svg)](https://academy.alkemy.org/)

# Ejercitación SQL Intermedio
## _Índices_

El objetivo de este ejercicio es poder visualizar la diferencia y el impacto que tienen los índices aplicados a una tabla.

Para visualizar el concepto de índices clousterizados, ingrese a https://sqliteonline.com/ utilizando el motor “MariaDB” y siga los pasos:

a-  Crear una tabla persona sin primary key y solamente con dos campos: id y nombre:   
  ```sql
    CREATE TABLE PERSONA (
        ID INT,
        NOMBRE VARCHAR(155)
    )
  ```
b- Inserte datos siguiendo un orden no secuencial para el id.
```sql
    INSERT INTO PERSONA (ID,NOMBRE) VALUES (
    '3',  'Renzo'); 
    INSERT INTO PERSONA (ID,NOMBRE) VALUES (
    '2',  'Renzo'); 
    INSERT INTO PERSONA (ID,NOMBRE) VALUES (
    '1',  'Renzo'); 
    INSERT INTO PERSONA (ID,NOMBRE) VALUES (
    '5',  'Renzo'); 
```

c- Consulte los datos para visualizar el orden de registros.
| Juego             | Compañia    | Clasificacion | Precio (MXN) |
|-------------------|-------------|---------------|--------------|
| Animal Crossing   | Nintendo    | E             | 1600         |
| Persona 5         | Atlus       | T             | 1500         |
| Final Fantasy VII | Square Enix | T             | 1500         |
| Fortnite          | Epic Games  | M             | 0            |
d- Agregue una clave primaria para el campo id.
e- Consulte los datos para visualizar el orden de registros.
