[![Alkemy Lab](https://academy.alkemy.org/images/alkemy-logo.svg)](https://academy.alkemy.org/)

# Ejercitación SQL I
## _Manipulación_

1-  Cree una tabla llamada CURSO con los atributos: 
  - Código de curso (clave primaria, entero no nulo) 
  - Nombre (varchar no nulo) 
  - Descripcion (varcha) 
  - Turno (varchar no nulo) 
  ```sql
    CREATE TABLE CURSO (
        CODIGO INT NOT NULL,
        NOMBRE VARCHAR(155) NOT NULL,
        DESCRIPCION VARCHAR (255),
        TURNO VARCHAR (15) NOT NULL,
        PRIMARY KEY (CODIGO)
    )
  ```
2- Agregue un campo “cupo” de tipo numérico
 ```sql 
    ALTER TABLE CURSO ADD CUPO INT;
 ```
3- Inserte datos en la tabla:
  - (101, “Algoritmos”,”Algoritmos y Estructuras de Datos”,”Mañana”,35)
  - (102, “Matemática Discreta”,””,”Tarde”,30)
```sql
 --opción 1
    INSERT INTO CURSO (CODIGO,NOMBRE,DESCRIPCION,TURNO,CUPO) 
    VALUES ('101','Algoritmos','Algoritmos y Estructuras de Datos','Mañana','35'); 
  --opción 2
    INSERT INTO CURSO VALUES ('102','Matemática Discreta','','Tarde','35');
```
4- Intente ingresar un registro con el nombre nulo y verifique que no funciona.
```sql
    INSERT INTO CURSO (CODIGO,DESCRIPCION,TURNO,CUPO) VALUES (
    '103',  'Computación Gráfica',  'Tarde',  '30'); 
```
![Error Nombre Null](https://raw.githubusercontent.com/devrebeleza/alkemy-sql/main/error_insert_sql.PNG)

5- Intente ingresar un registro con la clave primaria repetida y verifique que no funciona.
```sql
    INSERT INTO CURSO (CODIGO,NOMBRE,DESCRIPCION,TURNO,CUPO) 
    VALUES ('102', 'Informática', 'Computación Gráfica',  'Tarde',  '30'); 
```  
![Error Código repetido](https://raw.githubusercontent.com/devrebeleza/alkemy-sql/main/error_insert_cod_repetido_sql.PNG)

6- Actualice, para todos los cursos, el cupo en 25.
```SQL
    UPDATE CURSO SET CUPO = 25;
```

7- Elimine el curso Algoritmos.
```SQL
  --opción 1
    DELETE FROM CURSO WHERE NOMBRE = 'Algoritmos';
  --opción 2
    DELETE FROM CURSO WHERE NOMBRE LIKE '%Algoritmos%';
```

