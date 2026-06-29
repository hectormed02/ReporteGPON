# 🚀 Guía de Despliegue en Vercel

## Paso 1: Preparar GitHub

```bash
# Crear carpeta del proyecto
mkdir gpon-bbdd
cd gpon-bbdd

# Inicializar Git
git init
git add .
git commit -m "Initial commit: GPON BBDD Dashboard"

# Crear repositorio en GitHub.com
# (Crear repo en web: https://github.com/new)

# Conectar con remote
git remote add origin https://github.com/TU_USUARIO/gpon-bbdd.git
git branch -M main
git push -u origin main
```

## Paso 2: Desplegar en Vercel

### Método A: Desde Web UI de Vercel (Recomendado)

1. Ve a https://vercel.com
2. Click en "New Project"
3. Conecta tu cuenta GitHub
4. Busca "gpon-bbdd"
5. Click "Import"
6. **Framework:** Selecciona "Other"
7. **Build Command:** Deja vacío
8. Click "Deploy"

✅ ¡Vercel asignará automáticamente una URL!

### Método B: CLI de Vercel

```bash
# Instalar Vercel CLI
npm install -g vercel

# Iniciar sesión
vercel login

# Desplegar
vercel

# Responder preguntas:
# ? Set up and deploy "~/gpon-bbdd"? [Y/n] → Y
# ? Which scope do you want to deploy to? → Tu cuenta
# ? Link to existing project? [y/N] → N
# ? What's your project's name? → gpon-bbdd
# ? In which directory is your code? [./] → .
# ? Want to override the settings? [y/N] → N
```

## Paso 3: Configurar Dominio Personalizado (Opcional)

En https://vercel.com/dashboard:

1. Selecciona proyecto "gpon-bbdd"
2. Settings → Domains
3. Añade dominio personalizado
4. Configura DNS según indicaciones

## Paso 4: Actualizar Datos Automáticamente

Cada vez que hagas cambios:

```bash
# Editar datos/archivos localmente
# ...

# Hacer commit
git add .
git commit -m "Update: Datos GPON actualizados junio 2026"

# Push a GitHub
git push origin main

# ✅ Vercel redeploya automáticamente!
```

## Verificar Deploy

1. Ve a tu URL de Vercel (ej: `https://gpon-bbdd.vercel.app`)
2. Verifica que carguen los datos
3. Prueba filtros, búsqueda, exportación

## Solucionar Problemas

### Error: "Cannot find module"
- Verifica que index.html esté en root
- Asegúrate de que bbdd_data.json está presente

### Datos no aparecen
- Abre DevTools (F12) → Console
- Verifica que no hay errores de CORS
- Comprueba que bbdd_data.json es válido

### Necesito re-desplegar
```bash
# Forzar rebuild
vercel --prod
```

## Monitoreo

Vercel proporciona automáticamente:
- ✅ Analytics en dashboard
- ✅ Logs de deploy en tiempo real
- ✅ Notificaciones de error
- ✅ SSL/HTTPS automático

---

**¿Preguntas?** Revisa la documentación de Vercel: https://vercel.com/docs
