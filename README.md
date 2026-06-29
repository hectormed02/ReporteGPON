# 📊 GPON BBDD - Dashboard Comercial

Sistema web interactivo para gestión y análisis de ventas de fibra óptica GPON Entel Perú.

## 🚀 Características

✅ **Dashboard interactivo** con estadísticas en tiempo real
✅ **Filtros avanzados** por supervisor, estado, asesor y gestor  
✅ **Búsqueda global** en toda la base de datos
✅ **Paginación** de 10, 25, 50 o 100 registros
✅ **Exportación CSV** de datos filtrados
✅ **Diseño responsive** para móvil y escritorio
✅ **Paleta de colores Entel** (magenta, navy, cyan)
✅ **Cero dependencias backend** - Estático y seguro

## 📈 Datos Incluidos

- **141 registros** de ventas GPON (Junio 2026)
- Información de asesores, supervisores y gestores
- Estados de seguimiento (ADMITIDA, INSTALADO, PROSPECTO, ANULADO)
- Valores de ACCESS y planes de datos
- Identificadores PSI y OPP
- Fechas de ingreso y seguimiento

## 🌐 Desplegar en Vercel

### Opción 1: Desde GitHub UI
1. Fork este repositorio
2. Ve a [Vercel.com](https://vercel.com)
3. Conecta tu GitHub
4. Selecciona este repositorio
5. ¡Vercel lo desplegará automáticamente!

### Opción 2: CLI de Vercel
```bash
npm install -g vercel
cd gpon-bbdd
vercel
```

### Opción 3: Manual
```bash
git clone https://github.com/TU_USUARIO/gpon-bbdd.git
cd gpon-bbdd
# Subir archivos a Vercel
```

**URL de deploy:** `https://gpon-bbdd.vercel.app`

## 📁 Estructura del Proyecto

```
gpon-bbdd/
├── index.html          # App web principal
├── bbdd_data.json      # Datos embebidos
├── package.json        # Metadatos
├── vercel.json         # Config Vercel
├── .gitignore          # Archivos a ignorar
└── README.md           # Este archivo
```

## 🛠️ Tecnologías

- **Frontend:** HTML5 + Bootstrap 5 + jQuery
- **Tabla de datos:** DataTables.js
- **CDN:** jsDelivr, cdnjs.cloudflare.com
- **Hospedaje:** Vercel (gratuito)
- **Versionamiento:** GitHub

## 💻 Desarrollo Local

```bash
# Clonar repositorio
git clone https://github.com/TU_USUARIO/gpon-bbdd.git
cd gpon-bbdd

# Servidor local (Python)
python -m http.server 8000

# O con Live Server en VS Code
# Click derecho en index.html → "Open with Live Server"
```

Abre `http://localhost:8000` en tu navegador.

## 🔄 Actualizar Datos

Para actualizar los datos GPON:

1. **Exporta la hoja BBDD** de tu archivo Excel
2. **Convierte a JSON** con el script Python incluido
3. **Reemplaza** `bbdd_data.json`
4. **Push a GitHub** → Vercel se redeploya automáticamente

```python
import pandas as pd
import json

df = pd.read_excel('reporte.xlsx', sheet_name='BBDD')
json_data = df.to_json(orient='records', default_handler=str)

with open('bbdd_data.json', 'w') as f:
    f.write(json_data)
```

## 🎨 Personalización

Edita los colores en `index.html` (línea ~30):

```css
:root {
    --entel-magenta: #DC143C;
    --entel-navy: #003366;
    --entel-cyan: #0096C8;
}
```

## 📊 Estadísticas

| Métrica | Valor |
|---------|-------|
| Registros | 141 |
| Ventas Admitidas | 87 |
| Instaladas | 6 |
| En Proceso | 31 |
| Anuladas | 17 |

## 🔒 Seguridad

- ✅ Datos públicos solamente (no contiene información sensible)
- ✅ Sin backend (sin base de datos)
- ✅ HTTPS automático en Vercel
- ✅ Cumple GDPR (sin cookies de tracking)

## 📞 Soporte

Para actualizaciones o cambios:
1. Edita los archivos localmente
2. Commit y push a GitHub
3. Vercel redeploya automáticamente

## 📄 Licencia

Interno Entel Perú - 2026

---

**Última actualización:** Junio 2026
**Datos:** Base GPON Comercial
**Estado:** ✅ Producción
