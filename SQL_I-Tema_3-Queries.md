[![Alkemy Lab](https://academy.alkemy.org/images/alkemy-logo.svg)](https://academy.alkemy.org/)

# Ejercitación SQL I
## _Queries_

En este ejercicio haremos diferentes consultas Select aplicando lo visto anteriormente \
Dada la tabla:\
PROFESOR\
![Tabla](https://raw.githubusercontent.com/devrebeleza/alkemy-sql/main/images/tabla_profesor.PNG)

### Para cada caso, escriba la consulta correspondiente:

1- Nombre, apellido y fecha de nacimiento de todos los empleados, ordenado por fecha de nacimiento ascendente.
  ```sql
    SELECT nombre, apellido, fecha_nacimiento 
    FROM PROFESOR
    ORDER BY fecha_nacimiento
  ```
2- Todos los profesores cuyo salario sea mayor o igual a 65000.
 ```sql 
    SELECT * from PROFESOR WHERE salario >=65000
 ```
3- Todos los profesores que nacieron en la década del 80.   
```sql
 --opción 1
    SELECT * FROM PROFESOR WHERE fecha_nacimiento BETWEEN 1980-01-01 and 1980-12-31
--opción 2
    SELECT * FROM PROFESOR WHERE fecha_nacimiento >= 1980-01-01 and  fecha_nacimiento <= 1980-12-31
--opción 3 - MySQL - ORACLE - PostgreSQL
    SELECT * FROM PROFESOR WHERE extract( year FROM fecha_nacimiento) = 1980
```

4- (5) registros
```sql
    SELECT * FROM PROFESOR LIMIT 5;
```


5- Todos los profesores cuyo apellido inicie con la letra “P”
```sql
   SELECT * FROM PROFESOR WHERE apellido like 'P%' ;
```  
![Error Código repetido](https://raw.githubusercontent.com/devrebeleza/alkemy-sql/main/images/error_insert_cod_repetido_sql.PNG)

6- Los profesores que nacieron en la década del 80 y tienen un salario mayor a 80000
```SQL
    UPDATE CURSO SET CUPO = 25;
```

