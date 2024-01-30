Partiendo del diagrama entidad - relación de una tienda informática crea la base de datos y agrega los registros que se presentan a continuación:

Diagrama Entidad/Relación*

![image](https://github.com/leoandyaz/data-base/assets/133395965/d2d9cbd3-c64d-4e92-bafd-68f77104c02a)

      CREATE TABLE fabricante (
     ID INT(10) PRIMARY KEY NOT NULL UNIQUE,  
     Nombre VARCHAR(100) NOT NULL 
     );   
     
       CREATE TABLE producto( 
     ID INT(10) PRIMARY KEY NOT NULL UNIQUE,  
     Nombre VARCHAR(100 NOT NULL),  
     Precio DOUBLE NOT NULL,   
     codigo_fabricante INT(10) NOT NULL,
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

     INSERT INTO producto (ID,Nombre,Precio,codigo_fabricante)
     VALUES 
     (1,'Disco Duro SATA3 1TB','86.99','5'),
     (2,'Memoria RAM DDR4 8GB','120','6'),
     (3,'Disco SSD 1TB','150.99','4'),
     (4,'GeForce GTX 1050 Ti','185','7'),
     (5,'GeForce GTX 1056 Xtreme','755','6'),
     (6,'Monitor 24 LED Full HD','202','1'),
     (7,'Monitor 27 LED Full HD','245.99','1'),
     (8,'Portatil Yoga 520','559','2'),
     (9,'Portatil Idepad 320','444','2'),
     (10,'Impresora HP Deskjet 3720','59.99','3'),
     (11,'Impresora HP Laserjet Pro M26nw','180','3');
     
