# 🍸 Sosa's Vibes — Sistema de Bar

Sistema completo de operación para el garden bar **Sosa's Vibes**: pedidos por QR, panel de bartender en tiempo real y panel de gerencia con inventario, finanzas y control anti-robo.

## 📁 Las 3 apps

| Archivo | Quién lo usa | URL |
|---|---|---|
| `menu.html` | Clientes (QR en mesa) | `https://joshepemmanuelsosa-ctrl.github.io/Sosasvibes/menu.html` |
| `bartender.html` | Bartender (requiere login) | `https://joshepemmanuelsosa-ctrl.github.io/Sosasvibes/bartender.html` |
| `gerente.html` | Gerente (requiere login) | `https://joshepemmanuelsosa-ctrl.github.io/Sosasvibes/gerente.html` |

## ⚙️ Stack

- **Frontend:** HTML/CSS/JS vanilla (sin frameworks, sin build)
- **Backend:** Supabase (PostgreSQL + Realtime + Auth) — toda la lógica crítica vive en funciones RPC del servidor
- **Hosting:** GitHub Pages, deploy automático desde la rama `main` de este repositorio (requiere repo público — sin esto, GitHub no sirve Pages gratis)

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
- Día de negocio con corte a las 6:00am (no medianoche) — una noche que cierra a las 2-4am no se parte en dos cortes

## 🚀 Cómo actualizar

1. Edita el archivo en GitHub (o reemplázalo con "Upload files"), o haz push a `main`
2. GitHub Pages detecta el cambio y publica solo — en 1-2 minutos está en producción
3. Para regresar a una versión anterior: pestaña **History** del archivo → ver versión → restaurar, o `git revert`

## ⚠️ Reglas del proyecto

- Los cambios a la base de datos son **siempre aditivos** (nunca DROP/TRUNCATE)
- La lógica de dinero e inventario vive en Supabase, nunca en el navegador
- Las 3 apps llevan meta tags anti-caché — no quitar
