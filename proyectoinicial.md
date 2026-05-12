Como DBA del proyecto **Perfumería**, aquí están las entidades esenciales para la gestión del negocio:Aquí está el resumen de las **13 entidades** propuestas y su justificación:

<img width="920" height="575" alt="image" src="https://github.com/user-attachments/assets/0adcd08f-117f-4169-b509-fa06d75c0fb7" />

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


<img width="990" height="443" alt="image" src="https://github.com/user-attachments/assets/f4e63bcf-c65b-47ac-bea7-175ae9c3a5a0" />
<img width="1047" height="586" alt="image" src="https://github.com/user-attachments/assets/521ed6be-d115-46ee-b0bf-ae2716be8249" />
<img width="1027" height="452" alt="image" src="https://github.com/user-attachments/assets/c876c85c-8904-45a0-b66c-4a3b1c92cdcd" />
<img width="978" height="662" alt="image" src="https://github.com/user-attachments/assets/a183b600-a80c-46db-b849-a82cfc1eb46a" />
<img width="995" height="653" alt="image" src="https://github.com/user-attachments/assets/647a1b0b-b269-4d16-9f8c-710c9156874e" />
<img width="846" height="738" alt="image" src="https://github.com/user-attachments/assets/27614f3c-58d9-4d7b-8313-c5088495efd6" />
<img width="825" height="674" alt="image" src="https://github.com/user-attachments/assets/302141e9-21ce-44f7-a791-e7aa15d2eaec" />
<img width="889" height="554" alt="image" src="https://github.com/user-attachments/assets/d3a6c9ed-11c5-4490-8dc7-e62f139cb46b" />
<img width="770" height="213" alt="image" src="https://github.com/user-attachments/assets/83904669-fe12-407d-b2de-635ebc72d75e" />





¿Quieres que profundice en algún módulo en particular, como el esquema de descuentos y promociones, la gestión de fragancias por notas olfativas, o el modelo de fidelización de clientes?
