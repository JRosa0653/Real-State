# VendeTuCasa RD 🏠

Landing page de bienes raíces para capturar leads de propietarios que quieren vender.

## Estructura

```
realestate-site/
├── index.html      # Sitio completo (una sola página)
├── favicon.svg     # Ícono del sitio
├── vercel.json     # Configuración de Vercel
├── prompt.json     # Persona / skillset / mindset utilizado
└── README.md       # Este archivo
```

## ⚙️ Configurar el formulario (EmailJS)

El formulario envía los datos directamente a **jrosa0653@gmail.com** usando EmailJS (servicio gratuito, 200 emails/mes).

### Pasos:

1. **Crea cuenta gratuita** en [emailjs.com](https://www.emailjs.com)

2. **Agrega un servicio de email**
   - Ve a *Email Services* → *Add New Service*
   - Selecciona Gmail y conecta **jrosa0653@gmail.com**
   - Copia el **Service ID** (ej: `service_abc123`)

3. **Crea un template**
   - Ve a *Email Templates* → *Create New Template*
   - Usa este contenido sugerido:
   ```
   Asunto: Nueva solicitud de venta — {{from_name}}

   👤 Nombre: {{from_name}}
   📱 Teléfono: {{telefono}}
   📧 Email: {{from_email}}
   🏠 Dirección: {{direccion}}
   🏡 Tipo: {{tipo}} | Habitaciones: {{habitaciones}}
   📊 Estado: {{estado}}
   💰 Precio estimado: {{precio}}
   📝 Motivo: {{motivo}}
   💬 Notas: {{notas}}
   ```
   - Copia el **Template ID** (ej: `template_xyz789`)

4. **Obtén tu Public Key**
   - Ve a *Account* → *General* → **Public Key**

5. **Actualiza `index.html`** (líneas ~295-297):
   ```js
   const EMAILJS_SERVICE_ID  = 'service_abc123';   // ← tu Service ID
   const EMAILJS_TEMPLATE_ID = 'template_xyz789';  // ← tu Template ID
   const EMAILJS_PUBLIC_KEY  = 'abc123XYZ...';     // ← tu Public Key
   ```

> **Fallback automático**: Si el email falla, el formulario redirige a WhatsApp con todos los datos pre-llenados. ¡Nunca perderás un lead!

---

## 🚀 Deploy en Vercel

### Opción A — Arrastra y suelta (más fácil)
1. Ve a [vercel.com](https://vercel.com) e inicia sesión
2. Click en *Add New → Project*
3. Arrastra la carpeta `realestate-site` completa
4. Click *Deploy* — ¡listo en 30 segundos!

### Opción B — CLI
```bash
npm i -g vercel
cd realestate-site
vercel --prod
```

---

## 📱 WhatsApp

El botón flotante y los CTAs apuntan a:
`https://wa.me/18494530811`

Para cambiar el número, busca y reemplaza `18494530811` en `index.html`.

---

## 🖼️ OG Image

Para que el preview al compartir el link se vea bien, sube una imagen a:
`/og-image.jpg` (recomendado: 1200×630px, foto de una casa bonita)

O actualiza la URL en las meta tags `og:image` y `twitter:image` del `<head>`.

---

## Contacto configurado
- 📧 Email: jrosa0653@gmail.com
- 💬 WhatsApp: +1 (849) 453-0811
