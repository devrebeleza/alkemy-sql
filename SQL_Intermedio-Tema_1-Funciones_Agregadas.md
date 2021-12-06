[![Alkemy Lab](https://academy.alkemy.org/images/alkemy-logo.svg)](https://academy.alkemy.org/)

# Ejercitación SQL Intermedio
## _Funciones Agregadas_

El objetivo de este ejercicio es poder hacer consultas que obtengan datos en forma agregada. \

### Para cada caso, escriba la consulta correspondiente:

1- Escriba una consulta para saber cuántos estudiantes son de la carrera Mecánica.
![Tabla](https://lh4.googleusercontent.com/5XyplRSIhDmN82eEQXRCCwK3kzqt6sSppGBjq66uOm2m_p-53a46HWY_fTcER4asNJI5v7gf5W9rHsGiCwydwohCkm3O6lLUmDQw_hxAGIjIEY8xljcamXn9EjRE_H99xV-01X4)
  ```sql
    SELECT nombre, apellido, fecha_nacimiento 
    FROM PROFESOR
    ORDER BY fecha_nacimiento
  ```
2- Escriba una consulta para saber, de la tabla PROFESOR, el salario mínimo de los profesores nacidos en la década del 80.
 ```sql 
    SELECT * from PROFESOR WHERE salario >= 65000;
 ```
3- Para el siguiente modelo relacional.   
```sql
 --opción 1
    SELECT * FROM PROFESOR WHERE fecha_nacimiento BETWEEN '1980-01-01' and '1989-12-31'
--opción 2
    SELECT * FROM PROFESOR WHERE fecha_nacimiento >= '1980-01-01' and  fecha_nacimiento <= '1989-12-31'
--opción 3 - MySQL - ORACLE - PostgreSQL
    SELECT * FROM PROFESOR WHERE extract( year FROM fecha_nacimiento) between 1980 and 1989
```

4- Escriba las siguientes consultas:
Cantidad de pasajeros por país
Suma de todos los pagos realizados
Suma de todos los pagos que realizó un pasajero. El monto debe aparecer con dos decimales.
Promedio de los pagos que realizó un pasajero.
```sql
    SELECT * FROM PROFESOR LIMIT 5;
```
