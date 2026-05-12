Como DBA del proyecto **Perfumería**, aquí están las entidades esenciales para la gestión del negocio:Aquí está el resumen de las **13 entidades** propuestas y su justificación:


**Catálogo**
- `PRODUCTO` — entidad central con atributos específicos de perfumería (concentración, volumen, género)
- `CATEGORIA` — diferencia entre agua de colonia, EDP, EDT, etc.
- `MARCA` — marcas como Chanel, Dior, Versace con su país de origen

**Clientes y ventas**
- `CLIENTE` — datos del comprador para historial y fidelización
- `PEDIDO` — cabecera de cada venta (estado, fecha, total)
- `DETALLE_PEDIDO` — líneas del pedido con precio y descuento por ítem

**Compras y proveedores**
- `PROVEEDOR` — distribuidores o casas madre
- `COMPRA` — órdenes de reposición
- `DETALLE_COMPRA` — productos y cantidades por compra

**Inventario**
- `INVENTARIO` — stock actual y mínimo por producto para alertas de reposición

**Operación interna**
- `EMPLEADO` — vendedores, cajeros, administradores
- `ROL` — controla permisos dentro del sistema
- `METODO_PAGO` — efectivo, tarjeta, transferencia, etc.

---

¿Quieres que profundice en algún módulo en particular, como el esquema de descuentos y promociones, la gestión de fragancias por notas olfativas, o el modelo de fidelización de clientes?
