# 🧩 Estructura general - Pizzeria

La base de datos modela un sistema tipo app de comida (pizzería / delivery).

---

# 📦 Colecciones y su función
## 👤 customers

Guarda la información de los clientes.

**Campos importantes:**

`name`, `surname`

`phoneNumber`

`address` (objeto embebido con calle, ciudad, etc.)

👉 Representa quién realiza los pedidos.

---

## 👨‍🍳 employees

Guarda la información de los empleados.

**Campos importantes:**

`name`, `surname`

`NIF`

`phoneNumber`

`role` (chef o delivery)

`stores_id` (referencia a tienda)

👉 Representa quién trabaja en el negocio y su función.

---

## 🏪 stores

Guarda la información de las tiendas.

**Campos importantes:**

`address` (objeto embebido con dirección completa)

👉 Representa los locales físicos donde se preparan los pedidos.

---

## 🍕 products

Guarda los productos disponibles.

**Campos importantes:**

`name`, `description`

`price`

`type` (pizza, bebida, hamburguesa)

`category_pizza` (solo para pizzas)

👉 Representa lo que se puede pedir.

---

## 📦 orderDetails

Guarda los pedidos realizados.

**Campos importantes:**

`customers_id` (cliente)

`stores_id` (tienda)

`driver_id` (repartidor, opcional)

`products_id` (array de productos)

`type` (delivery o pickup)

`orderDate`, `deliveredDate`

`address` (para entregas)

👉 Representa cada compra realizada en el sistema.

---

## 🔄 Funcionamiento general

Un cliente (customers) hace un pedido (orderDetails)

El pedido pertenece a una tienda (stores)

Incluye uno o varios productos (products)

Si es delivery, lo gestiona un empleado (employees)

👉 Todo el sistema gira alrededor de los pedidos.