# Disparadores

Crea una base de datos llamada test que contenga una tabla llamada alumnos con las siguientes columnas.
Tabla alumnos:

id (entero sin signo)
nombre (cadena de caracteres)
apellido1 (cadena de caracteres)
apellido2 (cadena de caracteres)
nota (número real)

       Create table Alumnos(   
          ID INT(10) PRIMARY KEY NOT NULL UNIQUE,     
          Nombre VARCHAR(20) NOT NULL,     
          Apellido1 VARCHAR(20) NOT NULL,   
          Apellido2 VARCHAR(20) NOT NULL,   
          Nota FLOAT(24) NOT NULL
      );
      
      
Una vez creada la tabla escriba dos triggers con las siguientes características:

Trigger 1: trigger_check_nota_before_insert

Se ejecuta sobre la tabla alumnos.
Se ejecuta antes de una operación de inserción.
Si el nuevo valor de la nota que se quiere insertar es negativo, se guarda como 0.
Si el nuevo valor de la nota que se quiere insertar es mayor que 10, se guarda como 10.

       DELIMITER //

       CREATE TRIGGER trigger_check_nota_before_insert
       BEFORE INSERT  
       ON Alumnos
       FOR EACH ROW
       BEGIN
       	IF NEW.nota < 0 THEN
               SET NEW.nota = 0;
           ELSEIF NEW.nota > 10 THEN
               SET NEW.nota = 10;
           END IF;
       END//

Trigger2 : trigger_check_nota_before_update

Se ejecuta sobre la tabla alumnos.
Se ejecuta antes de una operación de actualización.
Si el nuevo valor de la nota que se quiere actualizar es negativo, se guarda como 0.
Si el nuevo valor de la nota que se quiere actualizar es mayor que 10, se guarda como 10.

    CREATE TRIGGER trigger_check_nota_before_update
       BEFORE UPDATE
       ON Alumnos
       FOR EACH ROW
       BEGIN
       	IF NEW.nota < 0 THEN
               SET NEW.nota = 0;
           ELSEIF NEW.nota > 10 THEN
               SET NEW.nota = 10;
           END IF;
       END//
       
       DELIMITER ;


Una vez creados los triggers escribe varias sentencias de inserción y actualización sobre la tabla alumnos y verifica que los triggers se están ejecutando correctamente.

        INSERT INTO Alumnos (ID, Nombre, Apellido1, Apellido2, Nota)
        VALUES
        (1, "Carlos", "Santillan", "Carrasco", -6),
        (2, "Leonardo", "Gutierrez", "Ortega", 8),
        (3, "Pedro", "Montes", "Tijuano", 18);
       
        UPDATE Alumnos SET Nota = 33 WHERE Nombre = "Juan
