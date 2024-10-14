# Users_MariaDB
1. Indica el nombre de las tablas que aparecen en tu base de datos mysql.
  - Comando ===> **SELECT TABLE_NAME, TABLE_TYPE, ENGINE, TABLE_ROWS, DATA_LENGTH, INDEX_LENGTH, CREATE_TIME
    FROM INFORMATION_SCHEMA.TABLES
    WHERE TABLE_SCHEMA = 'mysql';**
  - ![image](https://github.com/user-attachments/assets/f2162bc5-b865-4f14-b33b-021e2e7c49dd) 
2. Crea el usuario "Bego" con contraseña “BegIña” para que pueda acceder desde localhost.
  - Comando ===> **CREATE USER 'Bego'@'localhost' IDENTIFIED BY 'BegIña';**
  - ![image](https://github.com/user-attachments/assets/34acf4e6-fa18-4224-966f-53f6ddd2e350)
  - ![image](https://github.com/user-attachments/assets/f2562770-6168-4f01-8a2c-7dff46b566b5)
3. Crea el usuario "Mati" con contraseña “aMi90” para que pueda acceder desde el dominio lasalleinstitucion.es.
  - Comando ===> **CREATE USER 'Mati'@'lasalleinstitucion.es' IDENTIFIED BY 'aMi90';**
  - ![image](https://github.com/user-attachments/assets/51dc4caf-8ccb-4bf0-99b3-15ea642d72ad)
4. Crea el usuario "Mifi" con contraseña “Loplo45” para que pueda acceder desde el dominio lasalleinstitucion.es.
  - Comando ===> **CREATE USER 'Mifi'@'lasalleinstitucion.es' IDENTIFIED BY 'Loplo45';**
  - ![image](https://github.com/user-attachments/assets/46853bf7-4d7a-4359-a572-240b13b7a1b9)
6. Muestra los usuarios creados (los que están en la tabla user de la base de datos mysql). Indica la sentencia que has utilizado para mostrar esos usuarios.
  - Comando ===> **SELECT User, Host FROM mysql.user**
  - ![image](https://github.com/user-attachments/assets/72c51f55-0251-428a-9425-bef406831e06)
7. Muestra el usuario con el que te has logado, utilizando para ello una función. Indica la sentencia que has utilizado para ello.
  - Comando ===> **Select user()**
  - ![image](https://github.com/user-attachments/assets/12649ee1-2f9b-4283-96fe-c6751769104d)
8. Muestra los privilegios del usuario Bego. Indica la sentencia que has utilizado para ello.
  - Comando ===> **SHOW GRANTS FOR 'Bego'@'localhost'**
  - ![image](https://github.com/user-attachments/assets/18c55749-8232-49b8-9a8a-59d17d6650fe)
9. Muestra los privilegios del usuario con el que te has logado. Indica la sentencia que has utilizado para ello.
  - Comando ===> **SHOW GRANTS FOR CURRENT_USER()**
  - ![image](https://github.com/user-attachments/assets/b94bd1ce-b250-4dc4-a527-da7cce5e8194)
10. Concede permisos al usuario Bego de lectura y actualización sobre la tabla usuario.
  - Comando ===> GRANT SELECT, UPDATE ON mariadb_jc.usuario TO 'Bego'@'localhost'
  - FLUSH PRIVILEGES
  - ![image](https://github.com/user-attachments/assets/76e1fd7e-2df0-41be-a9e8-5bf73fa25ed2)
11. Conéctate como Bego y lanza una sentencia select y otra update sobre la tabla usuario. Lanza también una sentencia delete. Muestra las sentencias y sus efectos sobre la base de datos de la red social.
  - Comando ===> SELECT * FROM usuario
  - ![image](https://github.com/user-attachments/assets/32f0669d-e309-4042-9634-01fb5fd6110a)
  - Comando ===> Update usuario set nombre = 'Juan Carlos' Where nombre = 'Juancar'
  - ![image](https://github.com/user-attachments/assets/68a17087-5534-4bed-85a6-b9a815c09949)
  - Comando ===> Delete from usuario Where nombre = 'Marco'
  - ![image](https://github.com/user-attachments/assets/8ea7f469-837c-461b-a784-2d478eb04e70)
12. Concede permisos al usuario Mati de borrado sobre la tabla grupo.
  - Comando ===>GRANT DELETE ON mariadb_jc.grupo TO 'Mati'@'lasalleinstitucion.es'
  - FLUSH PRIVILEGES
  - ![image](https://github.com/user-attachments/assets/2b328635-7ad1-4712-9a6c-1bbc764f4d3b)
13. Crea el usuario Crispula con contraseña “rosita” para que pueda acceder desde el dominio lasalleinstitucion.es y con permiso de lectura, actualización y borrado sobre las tablas usuario, grupo y comentario. Concede además permisos a Crispula para que pueda conceder sus permisos a otros usuarios.
  - Comando ===> CREATE USER 'Crispula'@'lasalleinstitucion.es' IDENTIFIED BY 'rosita'
  - ![image](https://github.com/user-attachments/assets/f07dc4eb-e30e-4927-b253-b2d394202927)
  - Comando ===> GRANT SELECT, UPDATE, DELETE ON mariadb_jc.usuario TO 'Crispula'@'lasalleinstitucion.es' WITH GRANT OPTION
  - GRANT SELECT, UPDATE, DELETE ON mariadb_jc.usuario TO 'Crispula'@'lasalleinstitucion.es' WITH GRANT OPTION
  - GRANT SELECT, UPDATE, DELETE ON mariadb_jc.comentario TO 'Crispula'@'lasalleinstitucion.es' WITH GRANT OPTION
  - FLUSH PRIVILEGES
  - ![image](https://github.com/user-attachments/assets/27986ecf-99cd-4c99-8ea5-cc2e4f91e24d)
14. Conéctate con el usuario Crispula.
  - ![image](https://github.com/user-attachments/assets/1ecb7134-41df-4fde-baa9-9906dcf2ddc1)
15. Inserta un registro en la tabla comentario. Actualiza un registro de la tabla grupo. Muestra
las sentencias y su resultado al ejecutarlas sobre la base de datos de la red social.
  - Comando ===> MariaDB [mariadb_jc]> insert into comentario (nombre) values ('Gilbert')
  - MariaDB [mariadb_jc]> insert into comentario (nombre) values ('Juancar')
  - ![image](https://github.com/user-attachments/assets/0264c32c-7b30-4929-ac35-701fbb6ffc3d)
  - Comando ===> Update grupo set nombre = 'Marco' Where nombre = 'Juancar2'
  - ![image](https://github.com/user-attachments/assets/6bca3913-03bf-4467-b579-c648267056a0)
16. Concede permiso de borrado sobre la tabla usuario a Bego. Muestra la sentencia
utilizada y el resultado de su ejecución.
  - Comando ===> GRANT DELETE ON mariadb_jc.usuario TO 'Bego'@'localhost'
  - FLUSH PRIVILEGES
  - ![image](https://github.com/user-attachments/assets/2b11c754-e85c-4daf-9f81-013d5605dcca)
17. Concede permiso de lectura y actualización sobre la tabla grupo a Mati. Muestra la
sentencia utilizada y el resultado de su ejecución.
  - Comando ===> GRANT SELECT, UPDATE ON mariadb_jc.grupo TO 'Mati'@'lasalleinstitucion.es'
  - FLUSH PRIVILEGES;
  - ![image](https://github.com/user-attachments/assets/c61f7d3b-4659-432a-b93b-74fc1f33c627)
18. Vuelve a conectarte con tu usuario de mysql.
  - Comando ===> sudo mariadb
  - ![image](https://github.com/user-attachments/assets/b67c5c9d-33b1-4976-aef7-bdea46fa83c7)
19. Concede permisos totales sobre todas las tablas de la base de datos de la red social a
    mifi. Muestra la sentencia utilizada y el resultado de su ejecución.
  - Comando ===> GRANT ALL PRIVILEGES ON mariadb_jc.* TO 'Mifi'@'lasalleinstitucion.es';
  - FLUSH PRIVILEGES
  - ![image](https://github.com/user-attachments/assets/72d324c4-39a0-4793-a4e5-1d1eb20164c5)
20. Quítale permisos de borrado sobre todas las tablas de la base de datos de la red social a
Mifi. Muestra la sentencia utilizada y el resultado de su ejecución.
  - Comando ===> REVOKE DELETE ON mariadb_jc.* FROM 'Mifi'@'lasalleinstitucion.es'
  - FLUSH PRIVILEGES
  - ![image](https://github.com/user-attachments/assets/958c24e4-1dd0-47c1-8a01-73d6b9455b3c)
21. Muestra los usuarios creados y sus privilegios (los que estén en la tabla user de la base de
datos mysql). Indica la sentencia que has utilizado para mostrar esos usuarios.
  - Comando ===> SELECT User, Host, 
  - SELECT_PRIV, INSERT_PRIV, UPDATE_PRIV, DELETE_PRIV, 
  - CREATE_PRIV, DROP_PRIV, 
  - GRANT_PRIV, 
  - INDEX_PRIV, ALTER_PRIV 
  - FROM mysql.user;
  - ![image](https://github.com/user-attachments/assets/1f1bce17-5ebc-4ebe-9e72-bbc22f2899b4)
22. Cambia la contraseña del usuario Mifi modificando directamente la tabla user. Indica
la sentencia que has utilizado para ello.

23. ¿Has necesitado hacer FLUSH PRIVILEGES después de la sentencia anterior? Explica el porqué
y para qué sirve FLUSH PRIVILEGES.

24. ¿Puedo utilizar la función PASSWORD con GRANT? Justifica tu respuesta.

25. Elimina el usuario Mifli. Muestra la sentencia utilizada y el resultado de su ejecución.
