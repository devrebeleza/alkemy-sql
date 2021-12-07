[![Alkemy Lab](https://academy.alkemy.org/images/alkemy-logo.svg)](https://academy.alkemy.org/)

# Ejercitación SQL Intermedio
## _Querys anidadas_

En este ejercicio es continuaremos con la resolución de consultas aplicando funciones de agregación.

Siguiendo con el modelo relacional visto a lo largo de esta cápsula:
[![table](https://lh5.googleusercontent.com/6Iswr_A1NqaGhF0FZavLH0j4mUbN4rdaBQiJypP-k13uONL4p_qw1UXvzOdYNG6pYasJLANiVBCIjbbRMxGH9pQ2U5xhqnua8RxccNYHgS5x8zcGjSa1uAlBhfVHfoM_LWpBc2s)

  1- Escriba una consulta que devuelva la cantidad de profesores que dictan más de un curso en el turno Noche.
   
  ```sql
    SELECT count(distinct id) as cantidad_profesores_dictan_de_noche
    FROM PROFESOR p
    WHERE (SELECT count(*) FROM CURSO WHERE turno = 'Noche' and c.PROFESOR_id = p.id) > 1;
  ```
2- Escriba una consulta para obtener la información de todos los estudiantes que no realizan el curso con código 105.
```sql
   SELECT * FROM ESTUDIANTE e
   WHERE e.legajo NOT IN (SELECT ESTUDIANTE_legajo FROM INSCRIPCION WHERE CURSO_codigo = 105);
```
