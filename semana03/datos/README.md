# LD3 — TecnoAndina Retail (Semana 3)

Base de práctica del Laboratorio Dirigido N.° 03 de Fundamentos de Gestión de Datos (TECSUP 2026-II).
Datos inventados para práctica: no son ventas ni personas reales. Periodo: agosto y septiembre de 2026.

| Hoja | Filas | Columnas |
|---|---|---|
| clientes | 24 | id_cliente, nombre, ciudad |
| productos | 14 | id_producto, nombre_producto, categoria, precio_lista |
| pedidos | 42 | id_pedido, id_cliente, fecha_pedido, canal, total |
| detalles_pedido | 68 | id_detalle, id_pedido, id_producto, cantidad, precio_unitario |

Carga en Google Colab:

```python
import sqlite3
import pandas as pd

url = "https://raw.githubusercontent.com/Rociosayan/Repo_FDG_2026-2/main/semana03/datos/LD3_TecnoAndina_Retail.xlsx"
conexion = sqlite3.connect(":memory:")

clientes = pd.read_excel(url, sheet_name="clientes")
productos = pd.read_excel(url, sheet_name="productos")
pedidos = pd.read_excel(url, sheet_name="pedidos")
detalles_pedido = pd.read_excel(url, sheet_name="detalles_pedido")

clientes.to_sql("clientes", conexion, index=False)
productos.to_sql("productos", conexion, index=False)
pedidos.to_sql("pedidos", conexion, index=False)
detalles_pedido.to_sql("detalles_pedido", conexion, index=False)
```

Docente: Pilar Rocío Sayán Mejía
