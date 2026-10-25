# LC2 — MiniMarket normalizado (Semanas 3 y 4)

Base de práctica del Laboratorio Calificado N.° 02 de Fundamentos de Gestión de Datos (TECSUP 2026-II).
Datos inventados para práctica: no son ventas ni personas reales. Periodo: 1 al 6 de abril de 2026.

Archivo: `minimarket_normalizacion.db` (SQLite)

| Tabla | Filas | Columnas |
|---|---|---|
| ventas_original | 12 | id_venta, fecha, cliente, distrito_cliente, producto, categoria, local, distrito_local, cantidad, precio_unitario, total_venta |
| categorias | 4 | id_categoria, nombre_categoria |
| productos | 8 | id_producto, nombre_producto, id_categoria, precio_unitario |
| clientes | 7 | id_cliente, nombre_cliente, distrito_cliente |
| locales | 3 | id_local, nombre_local, distrito_local |
| ventas | 12 | id_venta, fecha, id_cliente, id_producto, id_local, cantidad |

Carga en Google Colab:

```python
import sqlite3
import pandas as pd
import urllib.request

url = "https://raw.githubusercontent.com/Rociosayan/Repo_FDG_2026-2/main/semana04/laboratorio_calificado_2/datos/minimarket_normalizacion.db"
urllib.request.urlretrieve(url, "minimarket_normalizacion.db")
conn = sqlite3.connect("minimarket_normalizacion.db")
print("Base de datos cargada correctamente.")
```

Docente: Pilar Rocío Sayán Mejía
