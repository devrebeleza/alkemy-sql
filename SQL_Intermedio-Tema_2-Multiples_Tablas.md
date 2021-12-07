[![Alkemy Lab](https://academy.alkemy.org/images/alkemy-logo.svg)](https://academy.alkemy.org/)

# Ejercitación SQL Intermedio
## _Multiples Tablas_

### Para el siguiente modelo relacional::

![Tabla](https://lh3.googleusercontent.com/H0OrPiaFu3RKjSoIhFUPJPbTdFGG4gu4S24qHmTSjaRV04QpYZbICRQ-Y6i-DnNCH6pxt0gqLYTbISTuIpAPmM73XXlOS228hhbpmg5DrrvbjD9UiW6hhwujnV8PGoSYq6ZCxSM)

Escriba la siguiente información:

1- Nombre, apellido y cursos que realiza cada estudiante
 ```sql
    SELECT p.nombre, p.apellido, c.nombre as curso
    FROM ESTUDIANTE as p inner join INSCRIPCION i ON i.ESTUDIANTE_legajo = p.legajo
    inner join CURSO c ON c.codigo = i.CURSO_codigo;
  ```
2- Nombre, apellido y cursos que realiza cada estudiante, ordenados por el nombre del curso
 ```sql
    SELECT COUNT(legajo) as 'cantidad_estudiantes_mecanica'
    FROM ESTUDIANTE
    WHERE carrera = 'Mecánica';
  ```
3- Nombre, apellido y cursos que dicta cada profesor
 ```sql
    SELECT COUNT(legajo) as 'cantidad_estudiantes_mecanica'
    FROM ESTUDIANTE
    WHERE carrera = 'Mecánica';
  ```
4- Nombre, apellido y cursos que dicta cada profesor, ordenados por el nombre del curso
 ```sql
    SELECT COUNT(legajo) as 'cantidad_estudiantes_mecanica'
    FROM ESTUDIANTE
    WHERE carrera = 'Mecánica';
  ```
5- Cupo disponible para cada curso (Si el cupo es de 35 estudiantes y hay 5 inscriptos, el cupo disponible será 30)
 ```sql
    SELECT COUNT(legajo) as 'cantidad_estudiantes_mecanica'
    FROM ESTUDIANTE
    WHERE carrera = 'Mecánica';
  ```
6- Cursos cuyo cupo disponible sea menor a 10
 ```sql
    SELECT COUNT(legajo) as 'cantidad_estudiantes_mecanica'
    FROM ESTUDIANTE
    WHERE carrera = 'Mecánica';
  ```

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
    SELECT c.nombre pais, count(idpasajero) as 'cantidad_pasajeros'
    FROM PASAJERO p inner join PAIS c on p.idpais = c.idpais
    GROUP BY c.nombre
```    
 - Suma de todos los pagos realizados
```sql
    SELECT SUM(monto + impuesto) as 'total_pagos'
    FROM PAGO
```    
 - Suma de todos los pagos que realizó un pasajero. El monto debe aparecer con dos decimales.
```sql
    SELECT p.idpasajero, ROUND(SUM(monto + impuesto),2) as 'total_pagos_pasajero'
    FROM PASAJERO p inner join PAGO f on p.idpasajero = f.idpasajero
    GROUP BY p.idpasajero
```    
 - Promedio de los pagos que realizó un pasajero.
```sql
    SELECT p.idpasajero, ROUND(AVG(monto + impuesto),2) as 'promedio_pagos_pasajero'
    FROM PASAJERO p inner join PAGO f on p.idpasajero = f.idpasajero
    GROUP BY p.idpasajero
```    
