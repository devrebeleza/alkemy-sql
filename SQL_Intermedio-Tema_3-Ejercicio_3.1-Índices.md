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
    '2',  'Adrian'); 
    INSERT INTO PERSONA (ID,NOMBRE) VALUES (
    '1',  'Valeria'); 
    INSERT INTO PERSONA (ID,NOMBRE) VALUES (
    '5',  'Agustina'); 
```

c- Consulte los datos para visualizar el orden de registros.
```sql
   SELECT * FROM PERSONA
  ```
  
| id             | NOMBRE    | 
|-------------------|-------------|
|  3   | Renzo    |
|  2         | Adrian       |
|  1 | Valeria |
|  5          | Agustina  |

d- Agregue una clave primaria para el campo id.
e- Consulte los datos para visualizar el orden de registros.
