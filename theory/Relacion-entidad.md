Ejemplo 1

        Realiza el modelo entidad-relación para una lista de libros.
      El modelo consta de 2 entidades y una relación.
      La primera es la entidad libro cuyos atributos serán ID, nombre y precio.
      La segunda es la entidad género cuyos atributos serán ID y nombre. 
      Los libros están relacionados con los géneros.
      Un libro solo puede tener un género, pero distintos libros pueden pertenecer al     
      mismo género. 

      
![image](https://github.com/leoandyaz/data-base/assets/133395965/8622882f-37c2-47c1-ab45-a6a219868990)

                CREATE TABLE Libros (    
                        ID INT UNIQUE NOT NULL PRIMARY KEY,    
                        nombre VARCHAR(100),    
                        Precio FLOAT,    
                        IDGen INT UNIQUE NOT NULL,    
                        FOREIGN KEY (IDGen)                         
                        REFERENCES Generos(ID)
                );
                
                CREATE TABLE Generos (
                        ID INT UNIQUE NOT NULL PRIMARY KEY,
                        nombre VARCHAR (100)
                );

Ejemplo 2 

        Realiza el modelo entidad-relación para una tienda en línea.
      Nuestra tienda cuenta con productos los cuales tienen una identificación única, nombre, descripción y precio.
      Tenemos registro de cada cliente donde se almacena su nombre, dirección y correo electrónico.
      Un cliente puede realizar compras de un producto a la vez y almacenamos la fecha en que se realiza.


![image](https://github.com/leoandyaz/data-base/assets/133395965/7cdd4eb6-6c97-4b8e-beaf-645363736eeb)

             Create table Productos (    
             ID INT UNIQUE NOT NULL PRIMARY KEY,    
             Nombre VARCHAR(50),    
             Descripcion VARCHAR(150),    
             Precio FLOAT (4)  
             ); 
             
             Create table Clientes (    
                     ID INT UNIQUE NOT NULL PRIMARY KEY,   
                     Nombre VARCHAR(50),    
                     Direccion VARCHAR(150),    
                     Correo VARCHAR (33)  
             );  
             
             CREATE TABLE Compras (	
                     ID INT UNIQUE NOT NULL PRIMARY KEY,       
                     Fecha DATE (33),    IDProd INT UNIQUE NOT NULL,        
                     IDClient INT UNIQUE NOT NULL,    
                     FOREIGN KEY (IDprod) REFERENCES Productos(ID),    
                     FOREIGN KEY (IDclient) REFERENCES Clientes(ID)
             ); 

Ejercicio universidad

      Realiza el modelo entidad-relación para una universidad. 
    De cada estudiante se tiene información como su número de identificación, nombre, dirección y fecha de nacimiento.
    De cada profesor se tiene un número de identificación, nombre, especialización y contacto.
    De cada curso en la universidad se tiene un código único, nombre y créditos asociados.
    Varios alumnos pueden estar inscritos a distintos cursos pero solo pueden ser impartidos por un profesor.


![image](https://github.com/leoandyaz/data-base/assets/133395965/35723226-3c65-4a41-beb5-9ad482e185b2)

Mdle

        La editorial tiene varias sucursales, con su domicilio, teléfono y un código de sucursal.

    Cada sucursal tiene varios empleados, de los cuales tendremos su nombre, apellidos, NIF y teléfono. Un empleado trabaja en una única sucursal.
    
    En cada sucursal se publican varias revistas, de las que almacenaremos su título, número de registro, periodicidad y tipo.
    
    Una revista puede ser publicada por varias sucursales.
    
    La editorial tiene periodistas (que no trabajan en las sucursales) que pueden escribir artículos para varias revistas. Almacenaremos los mismos datos que para los empleados, añadiendo su especialidad.




![image](https://github.com/leoandyaz/data-base/assets/133395965/f73992c0-1139-4abe-b893-ff5136e80ae4)

