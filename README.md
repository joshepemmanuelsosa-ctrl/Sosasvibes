# 🍸 Sosa's Vibes — Sistema de Bar

Sistema completo de operación para el garden bar **Sosa's Vibes**: pedidos por QR, panel de bartender en tiempo real y panel de gerencia con inventario, finanzas y control anti-robo.

## 📁 Las 3 apps

| Archivo | Quién lo usa | URL |
|---|---|---|
| `menu.html` | Clientes (QR en mesa) | `/menu.html` |
| `bartender.html` | Bartender (requiere login) | `/bartender.html` |
| `gerente.html` | Gerente (requiere login) | `/gerente.html` |

## ⚙️ Stack

- **Frontend:** HTML/CSS/JS vanilla (sin frameworks, sin build)
- **Backend:** Supabase (PostgreSQL + Realtime + Auth) — toda la lógica crítica vive en funciones RPC del servidor
- **Hosting:** Netlify con deploy automático desde este repositorio

## 🔑 Funciones principales

- Pedidos por mesa con configurador de bebidas (escarchado multi-paso)
- Seguimiento del pedido en tiempo real + cancelación controlada
- Pago con propina (calculada server-side) + ticket digital PNG
- Cobro blindado: sin dobles cobros, sin cobrar canceladas
- Edición total de órdenes desde bartender con devolución automática de inventario
- Inventario BOM: cada venta descuenta sus ingredientes exactos
- Conteo de cierre ciego (anti-robo) con historial de faltantes en $
- Alertas de stock bajo en el panel del bartender
- Módulo de cigarros, corte de caja con propinas, finanzas con márgenes

## 🚀 Cómo actualizar

1. Edita el archivo en GitHub (o reemplázalo con "Upload files")
2. Netlify detecta el cambio y publica solo — en ~1 minuto está en producción
3. Para regresar a una versión anterior: pestaña **History** del archivo → ver versión → restaurar

## ⚠️ Reglas del proyecto

- Los cambios a la base de datos son **siempre aditivos** (nunca DROP/TRUNCATE)
- La lógica de dinero e inventario vive en Supabase, nunca en el navegador
- Las 3 apps llevan meta tags anti-caché — no quitar
