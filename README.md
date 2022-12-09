# Tp-Base-de-datos-SQL

## Ejercicio 1

### *listar los nombres de los usuarios*

  SELECT tblusuarios.nombre AS nomreUsuario FROM tblusuarios;

## Ejercicio 2

### *Calcular el saldo maximo de los usurios de sexo mujer*

  SELECT nombre AS nombreUsuario ,MAX(saldo) AS saldoMaximo FROM tblusuarios WHERE tblusuarios.sexo = "M";

## Ejercicio 3

### *Listar nombre y teléfono de los usuarios con teléfono NOKIA, BLACKBERRY o SONY*

  SELECT nombre AS nombreUsuario, telefono, marca FROM tblusuarios WHERE marca IN ('NOKIA', 'BLACKBERRY', 'SONY');

## Ejercicio 4

### *Contar los usuarios sin saldo o inactivos*

  SELECT COUNT(*) AS usuariosSinSaldoOInactivos FROM tblusuarios WHERE saldo <= 0 OR activo = 0;

## Ejercicio 5

### *Listar el login de los usuarios con nivel 1, 2 o 3*

  SELECT nivel, usuario AS Login FROM tblusuarios WHERE nivel IN (1, 2, 3) order by nivel ASC LIMIT 21;

## Ejercicio 6

### *Listar los números de teléfono con saldo menor o igual a 300*

  SELECT nombre, telefono, saldo FROM tblusuarios WHERE saldo <= 300 ORDER BY saldo DESC;

## Ejercicio 7

### **Calcular la suma de los saldos de los usuarios de la compañia telefónica NEXTEL*

  SELECT SUM(saldo) AS sumaSaldos FROM tblusuarios WHERE compañia = 'NEXTEL';

## Ejercicio 8

### *Contar el número de usuarios por compañía telefónica*

  SELECT COUNT(usuario) AS numeroUsuarios, compañia FROM tblusuarios GROUP BY compañia;

## Ejercicio 9

### *Contar el número de usuarios por nivel*

  SELECT COUNT(usuario) AS numeroUsuarios, nivel FROM tblusuarios GROUP BY nivel;

## Ejercicio 10

### *Listar el login de los usuarios con nivel 2*

  SELECT usuario AS 'Usuarios con nivel 2' FROM tblusuarios WHERE nivel = 2;

## Ejercicio 11

### *Mostrar el email de los usuarios que usan gmail*

  SELECT usuario, email FROM tblusuarios WHERE email LIKE '%gmail.%';

## Ejercicio 12

### *Listar nombre y teléfono de los usuarios con teléfono LG, SAMSUNG o MOTOROLA*

  SELECT nombre, telefono FROM tblusuarios WHERE marca = 'LG' OR marca = 'SAMSUNG' OR marca = 'MOTOROLA';

### Otra forma de resolver

  SELECT nombre, telefono FROM tblusuarios WHERE marca  IN ('LG', 'SAMSUNG', 'MOTOROLA');

## Ejercicio 13

### *Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca LG o SAMSUNG*

  SELECT nombre AS 'Nombre Usuario', telefono, marca FROM tblusuarios WHERE marca NOT IN('LG','SAMSUNG');

## Ejercicio 14

### *Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL*

  SELECT usuario, telefono, compañia FROM tblusuarios WHERE compañia = 'IUSACELL';

### Otra forma de resolver

  SELECT usuario, telefono, compañia FROM tblusuarios WHERE compañia IN ('IUSACELL');

## Ejercicio 15

### *Listar el login y teléfono de los usuarios con compañia telefónica que no sea TELCEL*

  SELECT usuario, telefono, compañia FROM tblusuarios WHERE compañia NOT IN('TELCEL');

## Ejercicio 16

### *Calcular el saldo promedio de los usuarios que tienen teléfono marca NOKIA*

  SELECT AVG(saldo) AS 'Saldo Promedio marca NOKIA' FROM tblusuarios WHERE marca IN ('NOKIA');

## Ejercicio 17

### *Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL o AXEL*

  SELECT usuario, telefono, compañia FROM tblusuarios WHERE compañia IN ('IUSACELL', 'AXEL') LIMIT 50;

## Ejercicio 18

### *Mostrar el email de los usuarios que no usan yahoo*

  SELECT usuario, email FROM tblusuarios WHERE email NOT LIKE ('%yahoo.%') LIMIT 50;

## Ejercicio 19

### *Listar el login y teléfono de los usuarios con compañia telefónica que no sea TELCEL o IUSACELL*

  SELECT usuario, telefono, compañia FROM tblusuarios WHERE compañia NOT IN('TELCEL', 'IUSACELL');

## Ejercicio 20

### *Listar el login y teléfono de los usuarios con compañia telefónica UNEFON*

  SELECT usuario, telefono, compañia FROM tblusuarios WHERE compañia IN('UNEFON');

## Ejercicio 21

### *Listar las diferentes marcas de celular en orden alfabético descendentemente*

  SELECT DISTINCT marca FROM tblusuarios ORDER BY marca DESC

## Ejercicio 22

### *Listar las diferentes compañias en orden alfabético aleatorio*

  SELECT DISTINCT compañia FROM tblusuarios ORDER BY RAND()

## Ejercicio 23

### *Listar el login de los usuarios con nivel 0 o 2*

  SELECT usuario FROM tblusuarios WHERE nivel IN(0,2);

## EJercicio 24

### *Calcular el saldo promedio de los usuarios que tienen teléfono marca LG*

  SELECT AVG(saldo) AS 'PromedioSaldoMarcaLG' FROM tblusuarios WHERE marca IN ('LG');

## Ejercicio 25

### *Listar el login de los usuarios con nivel 1 o 3*

  SELECT usuario AS Login FROM tblusuarios WHERE nivel IN (1, 3);

## Ejercicio 26

### *Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca BLACKBERRY*

  SELECT nombre, telefono FROM tblusuarios WHERE marca NOT IN ('BLACKBERRY')

## Ejercicio 27

### *Listar el login de los usuarios con nivel 3*

  SELECT usuario AS Login FROM tblusuarios WHERE nivel = 3

## Ejercicio 28

### *Contar la cantidad de registros por sexo*

  SELECT sexo, COUNT(*) FROM tblUsuarios GROUP BY sexo;

## Ejercicio 29

### *Contar la cantidad de registros por marca*

  SELECT marca, COUNT(*) FROM tblUsuarios GROUP BY marca;

## Ejercicio 30

### *Listar las diferentes compañias en orden alfabético descendentemente*

  SELECT distinct(compañia) FROM tblusuarios ORDER BY compañia DESC

### Otra forma de resolver

  SELECT compañia FROM tblusuarios GROUP BY compañia DESC
