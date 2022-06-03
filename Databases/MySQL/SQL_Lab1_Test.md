
---

## Crear y eliminar `DB`

- Crear una `database` llamada `fz3r0_test01`_

    - `create database fz3r0_test01;`
    
    - ![image](https://user-images.githubusercontent.com/94720207/171761907-50f7878d-f19c-4a2d-bfd3-52a91308f4d5.png)

    - ![image](https://user-images.githubusercontent.com/94720207/171762049-837d103b-b298-4880-ae18-4f58eaf2c17f.png)

- Elimina `database` llamada `test`

    - `drop database fz3r0_test01`

- Nota: Meq uedaré al final con una DB llamada `fz3r0_db666`

## Crear y eliminar `Tablas`

1. Lo primero que se debe hacer es indicar la DB que se está utilizando:

    - `use fz3r0_test01;`

2. Después ya puedo crear una tabla (dentro de los paréntesis irán los nombres de los `campos` y `tipo de dato`):

    - [MySQL Datatypes](https://www.w3schools.com/mysql/mysql_datatypes.asp)

    - HINT: `id` siempre será `integer`

        - `create table Usuario(id int, email varchar(255), username varchar(50));`

    - Ejecutar y refrescar:
    
        - ![image](https://user-images.githubusercontent.com/94720207/171762888-df585a5b-86d9-46e6-a57d-3bf6e61db093.png)
        - ![image](https://user-images.githubusercontent.com/94720207/171762950-2af9c67b-ad87-4cf0-b3c9-cc81405f4c8c.png)

    - Ejemplo de selección de campo:
    
        - ![image](https://user-images.githubusercontent.com/94720207/171763105-f86db80b-4854-4521-9e56-b4427ecbaae4.png)

    - Ejemplo 2, utilizando Table inspector:
    
        - ![image](https://user-images.githubusercontent.com/94720207/171763337-7ecc5feb-7afe-43a1-8b98-e57ed6aba23a.png)
        - ![image](https://user-images.githubusercontent.com/94720207/171763390-c79043d0-6be8-4f32-976e-c427c18d325e.png)
        
- Para borrar la tabla solo se utiliza `drop` justo como con la `db`

    - `drop table Usuario`

## Alter Table

- Se utiliza para actualizar los `campos` de las tablas, agregarlos o quitarlos

- Agregar un campo `edad` a la tabla `usuario`:

    - `alter table Usuario add edad int;`

    - `alterar > tabla > Usuario > Agregar > Campo(edad) {tipo entero}`
    
    - ![image](https://user-images.githubusercontent.com/94720207/171767890-6fb80d4e-bb70-4513-88a7-c0e2ffc624ea.png)

- Quitar un campo

    - `alter table Usuario drop column edad;`
    
    - `alterar > tabla > Usuario > Quitar > Columna(edad)

- Modificar tipo de dato en una columna

    - `alter table Usuario modify column email varchar(50);` 
    
    - ![image](https://user-images.githubusercontent.com/94720207/171768256-be494e2a-8cf2-479a-abe8-b98393bcf60e.png)
    
    - ![image](https://user-images.githubusercontent.com/94720207/171768299-502d0d8c-b196-4ddc-81c9-726153e9c2fe.png)

## Insert y Update Table


 

 


     