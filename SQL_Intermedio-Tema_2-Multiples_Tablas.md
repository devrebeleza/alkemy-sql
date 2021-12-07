[![Alkemy Lab](https://academy.alkemy.org/images/alkemy-logo.svg)](https://academy.alkemy.org/)

# Ejercitación SQL Intermedio
## _Multiples Tablas_

### Para el siguiente modelo relacional::

![Tabla](https://lh3.googleusercontent.com/H0OrPiaFu3RKjSoIhFUPJPbTdFGG4gu4S24qHmTSjaRV04QpYZbICRQ-Y6i-DnNCH6pxt0gqLYTbISTuIpAPmM73XXlOS228hhbpmg5DrrvbjD9UiW6hhwujnV8PGoSYq6ZCxSM)

Escriba la siguiente información:

1- Nombre, apellido y cursos que realiza cada estudiante
 ```sql
    SELECT p.nombre, p.apellido, c.nombre as curso_asiste
    FROM ESTUDIANTE p INNER JOIN INSCRIPCION i ON i.ESTUDIANTE_legajo = p.legajo
    INNER JOIN CURSO c ON c.codigo = i.CURSO_codigo;
  ```
2- Nombre, apellido y cursos que realiza cada estudiante, ordenados por el nombre del curso
 ```sql
    SELECT p.nombre, p.apellido, c.nombre as curso
    FROM ESTUDIANTE p INNER JOIN INSCRIPCION i ON i.ESTUDIANTE_legajo = p.legajo
    INNER JOIN CURSO c ON c.codigo = i.CURSO_codigo
    ORDER BY c.nombre;
  ```
3- Nombre, apellido y cursos que dicta cada profesor
 ```sql
    SELECT p.nombre, p.apellido, c.nombre as curso_dicta
    FROM PROFESOR p INNER JOIN CURSO c ON c.PROFESOR_id = p.id;
  ```
4- Nombre, apellido y cursos que dicta cada profesor, ordenados por el nombre del curso
 ```sql
    SELECT p.nombre, p.apellido, c.nombre as curso_dicta
    FROM PROFESOR p INNER JOIN CURSO c ON c.PROFESOR_id = p.id
    ORDER BY c.nombre;
  ```
5- Cupo disponible para cada curso (Si el cupo es de 35 estudiantes y hay 5 inscriptos, el cupo disponible será 30)
 ```sql
   SELECT c.codigo as curso, c.cupo - cant_inscriptos as cupo_disponible
   FROM CURSO c INNER JOIN 
   (SELECT COUNT(i.numero) as cant_inscriptos, CURSO_codigo FROM INSCRIPCION i GROUP BY CURSO_codigo) i 
   ON c.codigo = i.CURSO_codigo
   GROUP BY c.codigo;
  ```
 
6- Cursos cuyo cupo disponible sea menor a 10
 ```sql
    SELECT c.codigo as curso, c.cupo - cant_inscriptos as cupo_disponible
    FROM CURSO c INNER JOIN 
    (SELECT COUNT(i.numero) as cant_inscriptos, CURSO_codigo FROM INSCRIPCION i GROUP BY CURSO_codigo) i 
    ON c.codigo = i.CURSO_codigo
    GROUP BY c.codigo
    HAVING c.cupo - cant_inscriptos < 10;
  ```
