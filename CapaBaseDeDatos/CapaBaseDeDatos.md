# Pruebas en la Capa de Base de Datos

## 1. Cláusula `SELECT`

**Objetivo:**
- Verificar que se puedan consultar todos los productos de la tienda.

**Pasos:**
- Para obtener todos los registros de la tabla `products`, se hara uso de la palabra reservada `SELECT` y se hace de la siguiente manera.

**Consulta SQL:**
```sql
SELECT * FROM products;
```
### Expectativas:

- La consulta debe retornar todos los registros existentes en la tabla `products`.

- Según los datos proporcionados, se esperan 3 registros:
````
id: 1, name: 'Laptop Acer', price: 799.99, category_id: 1
id: 2, name: 'Smartphone Samsung', price: 499.99, category_id: 1
id: 3, name: 'Tablet Lenovo', price: 299.99, category_id: 1
````
### Validación:

- Confirmar que se obtienen 3 registros.
- Verificar que los datos de cada producto coinciden con los esperados.

## 2. Consulta de Actualizacion - `UPDATE`
**Objetivo:**
- Verificar que se pueda actualizar la información de un producto.

**Pasos:**
Para actualizar valores en la tabla `products` se debe hacer uso de la palabra reservada `UPDATE`, se implementa de la siguiente manera.

**Consulta SQL:**
```sql
UPDATE products SET price = 749.99 WHERE id = 1;
```
- Seleccionar un producto existente para actualizar, como por ejemplo, el producto con id = 1.
- Actualizar el precio del producto a un nuevo valor.

### Expectativas:
- El producto con id = 1 debe tener ahora un `price` de `749.99.`

### Validación:

- Para validar que la actualizacion se realizo, se debe realizar consulta para verificar el cambio:

```sql
SELECT price FROM products WHERE id = 1;
```
- Confirmar que el precio actualizado es `749.99`.

## 3. Consulta eliminar - `DELETE`
**Objetivo:**
- Se debe verificar que se pueda eliminar un producto.

**Pasos:**
Para eliminar un valor en la tabla `products` se debe hacer uso de la palabra reservada `DELETE`, y se implementa de la siguiente manera.

**Consulta SQL:**
```sql
DELETE FROM products WHERE id = 3;
```
- Seleccionar un producto para eliminar, por ejemplo, el producto con id = 3.
- Eliminar el producto de la tabla products.

### Expectativas:

- El producto con id = 3 debe ser eliminado de la tabla `products`.

### Validación:

- Realizar un consulta con la palabra reservada `WHERE`, para seleccionar un valor especifico, en este caso el producto eliminado:

```sql
SELECT * FROM products WHERE id = 3;
```

- Confirmar que no se visualiza ningún registro.

## 4. Consulta JOIN
**Objetivo:**

- Se debe verificar que se puedan obtener los productos junto con su categoría.

**Pasos:**

- Realizar una consulta que una las tablas `products` y `categories` utilizando la palabra reservada `JOIN`, y la sentencia se escribe de la siguiente manera.

**Consulta SQL:**
```sql
SELECT p.id, p.name, p.price, c.name AS category_name FROM products p JOIN categories c ON p.category_id = c.id;
````
### Expectativas:

- La consulta debe retornar todos los productos junto con el nombre de su categoría.
- Los productos deben estar correctamente asociados a la categoría 'Electrónicos'.

### Validación:

- Verificar que cada producto tiene el campo category_name correspondiente.
- Confirmar que los datos coinciden con las relaciones definidas.

## 5. Creación del Trigger
**Objetivo:**
- Verificar que se active un trigger al insertar un nuevo producto en la tabla products para mantener actualizado el inventario en la tabla inventory.

**Pasos:**
`Nota:` Un trigger es un bloque de código que se ejecuta automáticamente en respuesta a ciertos eventos en una base de datos, como por ejemplo insert, update entre otros
- Crear un trigger que, después de insertar un nuevo producto, agregue una entrada en `inventory` con `quantity_available` inicializada en `0.`
**Consulta SQL para crear el trigger:**
```sql
CREATE TRIGGER trg_after_insert_product
AFTER INSERT ON products
FOR EACH ROW
BEGIN
    INSERT INTO inventory (product_id, quantity_available)
    VALUES (NEW.id, 0);
END;
```
- Se insertar un nuevo producto para activar el trigger.

**Consulta SQL para insertar el producto:** para realizar esta accion se emplea el uso de la palabra reservada `INSERT` y se usa asi:
```sql
INSERT INTO products (id, name, price, category_id) VALUES (4, 'Smartwatch Apple', 399.99, 1);
```
### Expectativas:

- Al insertar el nuevo producto, el trigger debe crear automáticamente una entrada en `inventory` con `quantity_available = 0`.

### Validación:

- Verificar que el nuevo producto se ha insertado correctamente en `products`:

```sql
SELECT * FROM products WHERE id = 4;
```

- Verificar que la entrada correspondiente se ha creado en `inventory:`

```sql
SELECT * FROM inventory WHERE product_id = 4;
```
- Confirmar que `quantity_available` es 0.

## 6. Stored Procedure
**Objetivo:**
- Crear un Stored Procedure que devuelva el nombre y la cantidad disponible de un producto en base a su ID.

**Pasos:**
- Crear el Stored Procedure que recibe un product_id y devuelve el name y quantity_available.

**Consulta SQL para crear el Stored Procedure:**
```sql
CREATE PROCEDURE GetProductInventory(IN prod_id INT)
BEGIN
    SELECT p.name, i.quantity_available
    FROM products p
    JOIN inventory i ON p.id = i.product_id
    WHERE p.id = prod_id;
END;
```

- Ejecutar el Stored Procedure con un product_id válido, por ejemplo, 1.
**Consulta SQL para ejecutar el Stored Procedure:**

```sql
CALL GetProductInventory(1);
```
### Expectativas:

- El Stored Procedure debe retornar el nombre del producto y la cantidad disponible.
### Validación:

- Confirmar que los datos devueltos corresponden al producto con `id = 1`.
- Verificar que `name` y `quantity_available` son correctos.

### Observaciones Adicionales

Integridad Referencial: Se debe asegurar que las claves foráneas están correctamente definidas;
- `products.category_id` debe ser una clave foránea que referencia `categories.id.`
- `inventory.product_id` debe ser una clave foránea que referencia `products.id.`

Manejo de Excepciones:
- Verificar el comportamiento al intentar actualizar o eliminar un producto que no existe.
- Comprobar que se generan los errores adecuados y que el sistema los maneja correctamente.

- `Consistencia de Datos:`Después de cada operación (UPDATE, DELETE, INSERT), asegurarse de que los datos en la base de datos reflejan los cambios esperados.
- Validar que no hay datos inconsistentes o huérfanos debido a las operaciones realizadas.

Pruebas de Concurrencia:
- Si es aplicable, probar cómo se comporta el sistema bajo operaciones concurrentes.
- Asegurar que los mecanismos de bloqueo y transacciones funcionan correctamente.
