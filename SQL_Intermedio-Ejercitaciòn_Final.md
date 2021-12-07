[![Alkemy Lab](https://academy.alkemy.org/images/alkemy-logo.svg)](https://academy.alkemy.org/)

# Ejercitación SQL Intermedio
## _Ejercitación final_

En esta cápsula se buscó ampliar los conocimientos de SQL en cuanto a la realización de consultas. Las consultas vistas fueron un poco más complejas con más de una tabla involucrada en la mayoría de los casos.

Si bien es difícil cubrir todos los casos posibles para las consultas, esta es la base inicial para crear consultas más complejas, combinando las estudiadas en esta cápsula.

A continuación, dejamos una última evaluación a modo de cierre.

Teniendo en cuenta el modelo relacional utilizado a lo largo de la cápsula: 
![table](https://lh3.googleusercontent.com/1AOeM9pWbnWnkBLNN2pvJgbB2RdfEKCo7ijDthWY65iR_X4iCl2ukYXKFPeoaIR8zEHjQkc3tEyG4pF78v98L_d18onER1fK19_8whhNkgpQotCkcPtRhHvAfcCCR86hekx2mryl=s0)

En el recuadro que aparece debajo, coloque la URL correspondiente al repo con las respuestas. 

1- Escriba una consulta que devuelva el legajo y la cantidad de cursos que realiza cada estudiante.
```sql
    SELECT ESTUDIANTE_legajo, count(1) as cantidad_cursos
    FROM INSCRIPCION I
    GROUP BY ESTUDIANTE_legajo;
  ```
2- Escriba una consulta que devuelva el legajo y la cantidad de cursos de los estudiantes que realizan más de un curso.
```sql
    SELECT ESTUDIANTE_legajo , count(1) as cantidad_cursos
    FROM INSCRIPCION I
    GROUP BY ESTUDIANTE_legajo
    HAVING count(1) > 1;
  ```
3- Escriba una consulta que devuelva la información de los estudiantes que no realizan ningún curso.
```sql
    SELECT *
    FROM ESTUDIANTE e
    WHERE e.legajo NOT IN (SELECT ESTUDIANTE_legajo FROM INSCRIPCION I);
  ```
4- Escriba para cada tabla, los index (incluyendo su tipo) que tiene cada una.
```sql
     
  ```
5- Liste toda la información sobre los estudiantes que realizan cursos con los profesores de apellido “Pérez” y “Paz”.
```sql
    SELECT *
    FROM ESTUDIANTE e
    WHERE e.legajo IN (SELECT ESTUDIANTE_legajo FROM INSCRIPCION i 
                       WHERE CURSO_codigo IN (SELECT codigo FROM CURSO c 
                                              INNER JOIN PROFESOR p 
                                              ON c.PROFESOR_id = p.id
                                              )
                       );
  ```
