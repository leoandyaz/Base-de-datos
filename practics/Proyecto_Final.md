Instrucciones:

1. Diseña el modelo entidad - relación del siguiente problema.
2. Crea el script para la base de datos.
3. Descarga el proyecto final.
4. Diseña una base de datos sobre proveedores de acuerdo a la información proporcionada.
5. Una vez resuelto el proyecto final, sube el archivo al espacio indicado y envía.


Proveedores

Tenemos que diseñar una base de datos sobre proveedores y disponemos de la siguiente información: 

* De cada proveedor conocemos su nombre, dirección, ciudad, provincia y 
un código de proveedor que será único para cada uno de ellos.
* Nos interesa llevar un control de las piezas que nos suministra cada proveedor. 
*Es importante conocer la cantidad de las diferentes piezas que nos suministra y en qué fecha lo hace. 
Tenga en cuenta que un mismo proveedor nos puede suministrar una pieza con el mismo código en diferentes fechas. 
* El diseño de la base de datos debe permitir almacenar un histórico con todas las fechas y 
las cantidades que nos ha proporcionado un proveedor.
*Una misma pieza puede ser suministrada por diferentes proveedores.
De cada pieza conocemos un código que será único, nombre, color, precio y categoría.
* Pueden existir varias categorías y para cada categoría hay un nombre y un código de categoría único.
Una pieza sólo puede pertenecer a una categoría.

![image](https://github.com/leoandyaz/Base-de-datos/assets/133395965/a2ecbc88-07b2-4468-94a0-475b4ce28a1e)



        CREATE TABLE Proveedor (
            ID INT PRIMARY KEY,
            nombre VARCHAR(255),
            direccion VARCHAR(255),
            ciudad VARCHAR(100),
            provincia VARCHAR(100)
        );
        
        CREATE TABLE Categoria (
            ID INT PRIMARY KEY UNIQUE,
            nombre VARCHAR(100)
        );
        
        CREATE TABLE Pieza (
            ID INT PRIMARY KEY,
            nombre VARCHAR(255),
            color VARCHAR(50),
            precio DECIMAL(10),
          	IDcat INT UNIQUE NOT NULL,
            FOREIGN KEY (IDcat) REFERENCES Categoria(ID) 
        );
        
        
        CREATE TABLE Suministro (
         	cantidad INT,
            fecha DATE,
         	IDpie INT UNIQUE NOT NULL,        
            IDpro INT UNIQUE NOT NULL,
            FOREIGN KEY (IDpie) REFERENCES Pieza(ID),
            FOREIGN KEY (IDpro) REFERENCES Proveedor(ID)
            );
        
