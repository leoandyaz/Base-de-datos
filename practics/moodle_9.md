# Operaciones en una Base de Datos.



* Lista el nombre de todos los productos que hay en la tabla producto.

      SELECT nombre
      FROM producto;

* Lista los nombres y los precios de todos los productos de la tabla producto.


      SELECT nombre, precio
      FROM producto;

* Lista todas las columnas de la tabla producto.

      SELECT *
      FROM producto; 
  
* Devuelve una lista con el nombre del producto, precio y nombre de fabricante de todos los productos de la base de datos.

  
      SELECT producto.nombre as "Producto", producto.precio, fabricante.nombre AS "Fabricante"
      FROM producto
      JOIN Fabricante
      ON Fabricante.id = Producto. Codigo_fabricante; 

 ## Subconsultas (En la cláusula WHERE)

* Devuelve todos los productos del fabricante Lenovo. (Sin utilizar INNER JOIN).

      SELECT Nombre
      FROM Producto
      WHERE CODIGO_FABRICANTE = (
        SELECT ID
        FROM Fabricante
        WHERE Nombre = "LENOVO"
        );
  
* Devuelve todos los datos de los productos que tienen el mismo precio que el producto más caro del fabricante Lenovo. (Sin utilizar INNER JOIN).
  
          SELECT *
          FROM Producto
          WHERE Precio = (
            SELECT MAX (Precio)
            FROM Producto
            WHERE Codigo_fabricante = (
              SELECT ID
              FROM Fabricante
              WHERE Nombre = "LENOVO"
              )
            );
      
* Lista el nombre del producto más caro del fabricante Lenovo.
