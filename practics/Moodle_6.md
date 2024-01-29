Partiendo del diagrama entidad - relación de una tienda informática crea la base de datos y agrega los registros que se presentan a continuación:

Diagrama Entidad/Relación*

![image](https://github.com/leoandyaz/data-base/assets/133395965/d2d9cbd3-c64d-4e92-bafd-68f77104c02a)

     CREATE TABLE fabricante (
     ID INT(10) PRIMARY KEY,  
     Nombre VARCHAR(100)  
     );   
     
     CREATE TABLE producto( 
     ID INT(10) PRIMARY KEY,  
     Nombre VARCHAR(100),  
     Precio DOUBLE,   
     codigo_fabricante INT(10),
     FOREIGN KEY (codigo_fabricante) REFERENCES fabricante(ID)          
     );


 Listado: Fabricante*

 ![image](https://github.com/leoandyaz/data-base/assets/133395965/b66c8ba8-eb1a-47b5-b779-cea038c90f22)

     INSERT INTO fabricante (ID,Nombre)
     VALUES 
     (1,'Asus'),
     (2,'Lenovo'),
     (3,'Hewlett - Packard'),
     (4,'Samsung'),
     (5,'Seagate'),
     (6,'Crucial'),
     (7,'Giganyte'),
     (8,'Huawei'),
     (9,'Xiamoi');

Listado: Productos*

![image](https://github.com/leoandyaz/data-base/assets/133395965/b3055c30-9dd5-4995-8dca-f46bb17321cb)
