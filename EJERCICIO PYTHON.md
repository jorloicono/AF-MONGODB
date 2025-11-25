# Laboratorio Avanzado: MongoDB con Python (`pymongo`)

En este laboratorio practicarás operaciones avanzadas con MongoDB usando Python. Cada sección contiene **desafíos sin solución**, pensados para que implementes el código por tu cuenta en Colab.

---

## 1️⃣ Configuración Inicial

- Conéctate a tu base de datos MongoDB (local o Atlas) usando Python y `pymongo`.
- Crea una base de datos llamada `tienda_avanzada` y una colección llamada `productos`.

> **Desafío:** Asegúrate de que tu colección esté vacía antes de comenzar los ejercicios.

---

## 2️⃣ Inserción de Datos

Inserta **al menos 10 productos** en la colección `productos` con los siguientes campos:

- `nombre` (string)
- `categoria` (string)
- `precio` (float)
- `stock` (int)
- `tags` (lista de strings)
- `fecha_ingreso` (fecha en formato ISO o `datetime`)

> **Desafíos:**
1. Crea al menos 3 categorías diferentes.
2. Asegúrate de que algunos productos tengan `stock` = 0.
3. Incluye al menos un producto con más de 3 tags.

---

## 3️⃣ Queries Avanzadas

1. Encuentra todos los productos de la categoría "Electrónica" cuyo precio sea mayor a 500.  
2. Busca productos que tengan la palabra "deportivo" **en los tags** y stock mayor a 20.  
3. Encuentra productos cuyo nombre **empiece con la letra "S"** y cuyo precio sea menor a 100.  
4. Muestra solo el `nombre` y `precio` de todos los productos, **sin mostrar `_id`**.  
5. Encuentra productos que tengan **al menos 2 tags** en común con una lista que tú determines.

---

## 4️⃣ Actualizaciones y Eliminaciones

1. Aumenta el `stock` en 5 para todos los productos de la categoría "Ropa".  
2. Cambia el `precio` de todos los productos que tengan más de 50 unidades en stock, incrementándolo en un 10%.  
3. Agrega un nuevo tag `"oferta"` a todos los productos cuyo precio sea mayor a 100.  
4. Elimina todos los productos con `stock` = 0.

---

## 5️⃣ Agregaciones y Estadísticas

1. Cuenta cuántos productos hay por categoría.  
2. Calcula el **precio promedio** de los productos por categoría.  
3. Encuentra la categoría con el producto más caro.  
4. Muestra los 3 productos con mayor stock.  
5. Crea una lista de productos que tengan más de 2 tags, ordenados por `precio` descendente, mostrando solo `nombre` y `tags`.

---

## 6️⃣ Bonus: Consultas Avanzadas

1. Encuentra productos cuya `fecha_ingreso` sea del último mes.  
2. Actualiza todos los productos agregando un campo `descuento` con valor 0, pero solo para la categoría "Electrónica".  
3. Encuentra productos cuyo `nombre` contenga la letra "a" **y** cuyo precio esté entre 50 y 200.  
4. Realiza un pipeline de agregación que devuelva **por cada categoría**: total de productos, precio promedio y el producto más caro.

---

