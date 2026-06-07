# Subir archivos a S3 — Consola AWS

## Contexto

Tienes dos archivos nuevos que el docente preparó antes de clase.  
Los vas a subir directamente a S3 RAW — sin pasar por la EC2.

> **Regla:** Si el archivo llega por correo, descarga, o lo prepara alguien del equipo  
> → va directo a S3 RAW desde tu computador.  
> La EC2 entra después, cuando hay que procesar.

---

## Archivos a subir

| Archivo | Carpeta destino en S3 |
|---|---|
| `interacciones_producto.parquet` | `raw/interacciones/` |
| `soporte_detalle.parquet` | `raw/soporte/` |

---

## Paso a paso

### 1. Abrir S3 en la consola AWS

```
Consola AWS → barra de búsqueda → S3 → Enter
```

---

### 2. Entrar a tu bucket

```
Buscar: udla2026-lab-alumnoXX
Click en el nombre del bucket
```

> Reemplaza **XX** con tu número de alumno.

---

### 3. Entrar a la carpeta RAW

```
Click en la carpeta: raw/
```

---

### 4. Crear carpeta interacciones

```
Click en: Create folder
Nombre:   interacciones
Click en: Create folder
```

---

### 5. Entrar a la carpeta interacciones y subir el archivo

```
Click en la carpeta: interacciones/
Click en: Upload
Click en: Add files
Seleccionar: interacciones_producto.parquet
Click en: Upload
```

Esperar hasta ver:

```
✅ Upload succeeded
```

---

### 6. Volver a RAW y crear carpeta soporte

```
← Volver a raw/
Click en: Create folder
Nombre:   soporte
Click en: Create folder
```

---

### 7. Subir soporte_detalle.parquet

```
Click en la carpeta: soporte/
Click en: Upload
Click en: Add files
Seleccionar: soporte_detalle.parquet
Click en: Upload
```

Esperar hasta ver:

```
✅ Upload succeeded
```

---

### 8. Verificar que todo llegó

Navegar a `raw/` y confirmar que ves estas carpetas:

```
raw/
├── api/
├── contactos/
├── empresas/
├── interacciones/     ← nueva
├── negocios/
├── renovaciones/
├── soporte/           ← nueva
├── tickets/
└── ventas/
```

---

## ¿Por qué Parquet y no CSV?

Estos archivos los preparó el docente directamente en Parquet  
porque son datos estructurados con tipos bien definidos.

Los CSV que ya tienes en RAW — ventas, renovaciones, tipo de cambio —  
llegaron así desde su fuente original.  
En la siguiente etapa, **Glue los convierte a Parquet en Stage**.

```
RAW     → el formato que llegó (CSV o Parquet)
STAGE   → todo Parquet, sin excepciones
```
