# E-Commerce Medellín: Modelo ER
## Base de Datos para Plataforma de Comercio Electrónico

---

Plataforma de comercio electrónico en Medellín que permite a usuarios registrarse, vender y comprar productos en línea.

### Usuarios y Especialización

Los **usuarios** `[ENTIDAD]` se registran con **documento** `[CLAVE 🔑]`, **nombre** `[ATRIBUTO]`, **apellido** `[ATRIBUTO]`, **fecha de nacimiento** `[ATRIBUTO]` y **dirección** `[COMPUESTO 📍]` (calle, ciudad, departamento, código postal). Pueden registrar múltiples **teléfonos** `[MULTIVALUADO {📞}]` y **correos** `[MULTIVALUADO {📧}]`. La **edad** `[DERIVADO ⚙️]` se calcula desde la fecha de nacimiento.

Todo usuario es `[ESPECIALIZACIÓN TOTAL Y DISJUNTA]` **cliente** `[ENTIDAD]`, **vendedor** `[ENTIDAD]` o **administrador** `[ENTIDAD]`. Los clientes acumulan **puntos de fidelidad** `[ATRIBUTO]`. Los vendedores tienen **nombre de tienda** `[ATRIBUTO]`, **calificación** `[ATRIBUTO]` y **cuenta bancaria** `[ATRIBUTO]`.

### Productos y Categorías

Los vendedores **publican** `[1:N]` **productos** `[ENTIDAD]` con **nombre**, **descripción**, **precio**, **stock**, **peso** y **dimensiones** `[COMPUESTO 📍]` (alto, ancho, profundidad). Cada producto **pertenece a** `[N:1]` una **categoría** `[ENTIDAD]`.

### Pedidos y Pagos

Los clientes **realizan** `[1:N]` **pedidos** `[ENTIDAD]` con **fecha**, **estado** y **valor total** `[DERIVADO ⚙️]`. Cada pedido **contiene** `[N:M]` productos mediante **detalle_pedido** `[ENTIDAD DÉBIL ⚠️]`, que registra **cantidad**, **precio unitario** y **subtotal** `[DERIVADO ⚙️]`. Cada pedido **genera** `[1:1]` un **pago** `[ENTIDAD]` con **fecha**, **monto**, **método** y **estado**.

---

## Leyenda

| Símbolo | Tipo |
|---------|------|
| 🔑 | Clave |
| 📍 | Compuesto |
| {📧} | Multivaluado |
| ⚙️ | Derivado |
| ⚠️ | Entidad débil |

## Resumen

**9 Entidades:** Usuario, Cliente, Vendedor, Administrador, Producto, Categoría, Pedido, Detalle_Pedido, Pago

**6 Relaciones:** ES_UN, Publica (1:N), Pertenece_a (N:1), Realiza (1:N), Contiene (N:M), Genera (1:1)

---

_Modelo ER - E-Commerce Medellín_
