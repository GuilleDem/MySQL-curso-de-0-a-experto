# MySQL-curso-de-0-a-experto
Practica del curso de mysql

Curso MySQL de 0 a EXPERTO

cap 01 crear base de datos

comentario en linea

/*
comentario largo
*/

## creo una base de datos.
## el lugar donde se almacenan las base de datos MySQL lo llama SCHEMAS, puedo crear base de datos con el 4to ícono que tiene un mas.
CREATE DATABASE base_de_pratica

## uso/llamo a la BASE DE DATOS creada que quiero modificar
USE base_de_pratica

## creo una nueva base de datos
CREATE DATABASE Base_De_Practica

## esto nos muestra todas nuestras bases de datos creadas
SHOW DATABASES

#-------------------------------------fin capitulo
# cap 07 insertar datos

USE base_de_practica

## nos muestra las tablas que hay en una data base
SHOW TABLES

## insertar datos en una tabla
INSERT INTO nombre_tabla_uno (NOMBRE, APELLIDO, DNI, NACIMIENTO),
VALUES ("Carlos", "Velloz" "34546776", "121126") ;

## otra opción
## IMPORTAR ARCHIVO_CSV > CLIC derecho en la tabla > Table Data Import Wizard 

SELECT * FROM nombre_tabla_uno

#-------------------------------------fin capitulo
# cap 09 borrar registros

## eliminar un registro de la tabla
DELETE FROM nombre_tabla_uno
WHERE NOMBRE = "Carlos";

DELETE FROM nombre_tabla_uno
WHERE NOMBRE <> "Carlos";

#-------------------------------------fin capitulo
# cap 18 Modificaciones

## modificar una tabla
USE base_de_pratica
ALTER TABLE nombre_tabla_uno 
RENAME nueva_tabla

## borrar columna
ALTER TABLE nueva_tabla
DROP COLUMN NOMBRE, COLUMN APELLIDO;

## añadir una columna
ALTER TABLE nueva_tabla 
ADD NOMBRE VARCHAR (15);

## añadir una columna DESPUES de
ALTER TABLE nueva_tabla 
ADD APODO VARCHAR (15)
AFTER APELLIDO ; 

## añadir una columna en PRIMERA posición
ALTER TABLE nueva_tabla 
ADD ID VARCHAR (5)
FIRST; 

## cambiar el nombre y tipo de dato de una columna
ALTER TABLE nueva_tabla 
CHANGE ID PRUEBA VARCHAR (9);

## eliminar la FK Foreign de una tabla HIJA
ALTER TABLE nueva_tabla  
DROP FOREIGN KEY DNI;

## eliminar la PK Primary key de una tabla PADRE
ALTER TABLE nueva_tabla_principal 
DROP PRIMARY KEY;

DESCRIBE nueva_tabla # para ver la tabla

#-------------------------------------fin capitulo
# cap 08 operadores relacionales
/*
= IGUAL
<> DISTINTO
> MAYOR
< MENOR
>=MAYOR O IGUAL
<=MENOR O IGUAL
*/

SELECT NOMBRE, APELLIDO, DNI FROM nueva_tabla
WHERE DNI = 33445667;

#-------------------------------------fin capitulo
# cap 11 BETWEEN + IN 

SELECT * FROM base_de_practica.nueva_tabla
WHERE N°USUARIO NOT IN (3,6,9);

SELECT * FROM base_de_practica.nueva_tabla
WHERE N°USUARIO 
BETWEEN 3 AND 5 OR NOMBRE= "Carlos";

#-------------------------------------fin capitulo
# cap 13 funciones agregadas SUM COUNT MIN MAX 

USE USUARIO
SELECT * FROM USUARIO # Para ver la tabla

SELECT SUM(N° USUARIO) FROM primera.USUARIO;

SELECT COUNT(NOMBRE) FROM primera.USUARIO
WHERE NOMBRE = "Marcos";

SELECT MIN(N° USUARIO) FROM primera.USUARIO;

SELECT MAX(N° USUARIO) FROM primera.USUARIO;

#-------------------------------------fin capitulo
# cap 14 GROUP BY

SELECT NOMBRE, COUNT(N°USUARIO) FROM primera.USUARIO
GROUP BY NOMBRE;

SELECT NOMBRE, SUM(N°USUARIO) FROM primera.USUARIO
WHERE APELLIDO = "Castro" OR "Perez"
GROUP BY NOMBRE;

#-------------------------------------fin capitulo
# cap 15 HAVING + GROUP BY 

SELECT NOMBRE, SUM(N°USUARIO) FROM primera.USUARIO
GROUP BY NOMBRE
HAVING COUNT(N° USUARIO) >2;

#-------------------------------------fin capitulo
# cap 16 ORDER BY ASC/ DESC

SELECT * FROM primera.USUARIO
WHERE NOMBRE = "Carol" OR NOMBRE = "Marcos"
ORDER BY N° USUARIO ASC;

SELECT * FROM primera.USUARIO
WHERE NOMBRE = "Carol" OR NOMBRE = "Marcos"
ORDER BY N° USUARIO DESC;

#-------------------------------------fin capitulo
# cap 24 DISTINCT

SELECT DISTINCT NOMBRE FROM USUARIO # me devuelve un unico valor, distintos enter si

SELECT COUNT(DISTINCT NOMBRE) FROM USUARIO

----------------------------- FIN ------------------------------
