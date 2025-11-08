# 🚀 Instrucciones para Deploy en Vercel

## Solución del Error 404

El error 404 en Vercel ocurre porque necesitas un archivo `index.html` como punto de entrada principal.

## ✅ Solución Aplicada

He creado `index.html` (copia de `cholula.html`) que es el archivo que Vercel busca por defecto.

## 📤 Pasos para Deploy

### 1. Subir archivos a GitHub

```bash
# En tu repositorio de GitHub
git add index.html
git add cholula.html
git commit -m "Añadir index.html para Vercel"
git push origin main
```

### 2. Configurar Vercel

1. Ve a tu proyecto en [Vercel Dashboard](https://vercel.com/dashboard)
2. Ve a **Settings** → **General**
3. Configura:
   - **Framework Preset:** `Other`
   - **Build Command:** *(dejar vacío)*
   - **Output Directory:** *(dejar vacío)*
   - **Root Directory:** `./` o dejar vacío

### 3. Redeploy

1. Ve a **Deployments**
2. Click en el último deployment
3. Click en **Redeploy**

O simplemente haz un nuevo commit y push - Vercel redeployará automáticamente.

## 🔍 Verificación

Una vez desplegado, verifica:
- ✅ `https://[tu-proyecto].vercel.app` carga correctamente
- ✅ No aparece error 404
- ✅ Los videos cargan correctamente
- ✅ La navegación funciona
- ✅ El diseño responsive funciona

## 🆘 Si Aún Hay Problemas

### Alternativa 1: Archivo vercel.json
Crea `vercel.json` en la raíz:

```json
{
  "routes": [
    {
      "src": "/",
      "dest": "/index.html"
    }
  ]
}
```

### Alternativa 2: Carpeta public
Si prefieres mantener organización:

```
repo/
├── public/
│   └── index.html
├── package.json (opcional)
└── vercel.json
```

## 📝 Notas Importantes

- ✅ Asegúrate de que `index.html` esté en la **raíz del repositorio**
- ✅ No necesitas carpeta `dist` o `build`
- ✅ No necesitas `package.json` para este proyecto
- ✅ Vercel detectará automáticamente el HTML

## 🌐 Resultado Final

Tu presentación estará disponible en:
- **Production:** `https://[nombre-proyecto].vercel.app`
- **Preview:** URLs de preview para cada branch/pull request

---

**¿Tienes dudas?** Revisa la documentación de Vercel: https://vercel.com/docs

