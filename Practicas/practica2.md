
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
11. Conéctate como Bego y lanza una sentencia select y otra update sobre la tabla usuario. Lanza también una sentencia delete. Muestra las sentencias y sus efectos sobre la base de datos de la red social.
12. Concede permisos al usuario Mati de borrado sobre la tabla grupo.
13. Crea el usuario Crispula con contraseña “rosita” para que pueda acceder desde el dominio lasalleinstitucion.es y con permiso de lectura, actualización y borrado sobre las tablas usuario, grupo y comentario. Concede además permisos a Crispula para que pueda conceder sus permisos a otros usuarios.
14. Conéctate con el usuario Crispula.
