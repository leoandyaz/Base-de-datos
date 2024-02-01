# Funciones en SQL

* Calcula el número total de productos que hay en la tabla productos.

       SELECT count(nombre) as Total_productos from producto;
  
* Muestra el número total de productos que tiene cada uno de los fabricantes. El listado también debe incluir los fabricantes que no tienen ningún producto. El resultado mostrará dos columnas, una con el nombre del fabricante y otra con el número de productos que tiene. Ordene el resultado descendentemente por el número de productos.

       SELECT fabricante.nombre AS fabricante, COUNT(producto.id) AS numero_productos
       FROM fabricante
       LEFT JOIN producto ON fabricante.id = producto.codigo_fabricante
       GROUP BY fabricante.id, fabricante.nombre
       ORDER BY numero_productos DESC;


* Muestra el precio máximo, precio mínimo y precio medio de los productos de cada uno de los fabricantes. El resultado mostrará el nombre del fabricante junto con los datos que se solicitan.


* Muestra el nombre de cada fabricante, junto con el precio máximo, precio mínimo, precio medio y el número total de productos de los fabricantes que tienen un precio medio superior a 200€. Es necesario mostrar el nombre del fabricante.
