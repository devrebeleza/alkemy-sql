[![Alkemy Lab](https://academy.alkemy.org/images/alkemy-logo.svg)](https://academy.alkemy.org/)

# Ejercitación SQL Intermedio
## _Funciones Agregadas_

El objetivo de este ejercicio es poder hacer consultas que obtengan datos en forma agregada. \

### Para cada caso, escriba la consulta correspondiente:

1- Escriba una consulta para saber cuántos estudiantes son de la carrera Mecánica.
![Tabla](https://lh4.googleusercontent.com/5XyplRSIhDmN82eEQXRCCwK3kzqt6sSppGBjq66uOm2m_p-53a46HWY_fTcER4asNJI5v7gf5W9rHsGiCwydwohCkm3O6lLUmDQw_hxAGIjIEY8xljcamXn9EjRE_H99xV-01X4)
  ```sql
    SELECT COUNT(legajo) as 'cantidad_estudiantes_mecanica'
    FROM ESTUDIANTE
    WHERE carrera = 'Mecánica';
  ```
  
2- Escriba una consulta para saber, de la tabla PROFESOR, el salario mínimo de los profesores nacidos en la década del 80.
![Tabla](https://lh5.googleusercontent.com/zJIEvMS6oC-tCp-SJC3p0H9-VtNkiQIdYlpufSh4CpjCt6owniilN20rhknlOnHK0K3JGseWYrIF2js_zcm0ZmTlzDtoT7At8s9x1p944_g_0hoZxWdA37ccKS9GKCc7bOC8gDQ)
 ```sql 
    SELECT MIN(salario) as 'salario_minimo_profesor'
    FROM PROFESOR
    WHERE extract( year FROM fecha_nacimiento) between 1980 and 1989;
 ```
 
3- Para el siguiente modelo relacional.   
![Tabla](https://lh4.googleusercontent.com/3gu9oBjE6bgmxXbWnMPj0E4jpGiIXDVcpqNdY7Dn54yS-sPb2nes8peGjq82bpF-wHJ-iU9P68ofIFUGEJFwU2E6fheNHkbKwt9QMuUmWcVa3sW4zLDaofcZozEAGaJnEGZFAYg)


4- Escriba las siguientes consultas:
 - Cantidad de pasajeros por país
```sql
 -- 1
    SELECT count(idpasajero) as 'cantidad_pasajeros', c.nombre pais
    FROM PASAJERO p inner join PAIS c on p.idpais = c.idpais
    GROUP BY c.nombre
```    
 - Suma de todos los pagos realizados
 - Suma de todos los pagos que realizó un pasajero. El monto debe aparecer con dos decimales.
 - Promedio de los pagos que realizó un pasajero.

```sql
 -- 1
    SELECT count(idpasajero) as 'cantidad_pasajeros', c.nombre pais
    FROM PASAJERO p inner join PAIS c on p.idpais = c.idpais
    GROUP BY c.nombre
    
 -- 2
    SELECT * FROM PROFESOR WHERE fecha_nacimiento >= '1980-01-01' and  fecha_nacimiento <= '1989-12-31'
 -- 3 - MySQL - ORACLE - PostgreSQL
    SELECT * FROM PROFESOR WHERE extract( year FROM fecha_nacimiento) between 1980 and 1989
 -- 3 - MySQL - ORACLE - PostgreSQL
    SELECT * FROM PROFESOR WHERE extract( year FROM fecha_nacimiento) between 1980 and 1989
```
