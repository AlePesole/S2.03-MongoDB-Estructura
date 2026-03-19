# 🧩 Estructura general - OpticStore

Este modelo representa un sistema de **venta de gafas** (óptica).

---

# 📦 Colecciones y su función

## 👤 `customers`

Guarda la información de los clientes.

**Campos importantes:**

* `name`, `email`, `phone`
* `address` (objeto embebido con ciudad, calle, etc.)
* `registrationDate`
* `recommendedBy` (referencia a otro cliente)

👉 Representa quién compra.

---

## 👓 `glasses`

Contiene los productos disponibles.

**Campos importantes:**

* `brand`
* `frame` (tipo y color)
* `glass_left` y `glass_right` (graduación)
* `price`
* `provider_id` (quién suministra las gafas)

👉 Representa lo que se vende.

---

## 🧾 `sales`

Es la colección más importante (núcleo del sistema).

**Campos:**

* `customers_id` → cliente
* `employee_id` → empleado que atendió
* `glasses_id` → lista de gafas vendidas
* `saleDate`
* `total_price`

👉 Representa cada transacción.

---

## 🧑‍💼 `employee`

Información básica de empleados.

**Campos:**

* `name`

👉 Representa quién realiza la venta.

---

## 🚚 `provider`

Datos de proveedores.

**Campos:**

* `name`, `phone`, `NIF`
* `address`

👉 Representa quién suministra las gafas.

---

## ⚙️ Funcionamiento general

1. Se registra un cliente en `customers`
2. Se registran gafas en `glasses` (con su proveedor)
3. Un empleado vende gafas
4. Se crea un documento en `sales` que:

   * apunta al cliente
   * apunta al empleado
   * incluye las gafas compradas
   * guarda el total