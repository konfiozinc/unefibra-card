# UneFibra SAS — Tarjeta digital

Tarjeta digital de **UneFibra SAS** (internet por fibra óptica, Medellín).
Clon de la estructura de la tarjeta de Mega Express, con la **paleta y el logo reales de UneFibra**.

- **Sitio:** https://konfiozinc.github.io/unefibra-card/
- **Landing completa del cliente:** https://konfiozinc.github.io/unefibra/
- **WhatsApp:** [+57 304 465 4987](https://wa.me/573044654987)
- **Llamadas:** [+57 321 749 0310](tel:+573217490310)
- **Correo:** unefibrasas@gmail.com

## Editar el contenido

Todo lo editable está en **`CONFIG`** al inicio de `scripts.js`:

| Campo | Qué controla |
|---|---|
| `cliente` | nombre visible, profesión y eslogan del hero |
| `contacto` | WhatsApp, teléfono de llamadas, mensaje pre-armado y correo |
| `servicios` | los 4 diferenciadores (modal Servicios) |
| `planes` | los 5 planes y sus precios (sección "Planes de internet") |
| `cobertura` | texto y chips de zonas cubiertas |
| `informacion` | horarios, dirección y líneas de teléfono del modal Información |
| `colores` | paleta (también pinta el QR) |

> ⚠️ **Dos líneas distintas, no unificar:** WhatsApp (`304 465 4987`) y llamadas
> (`321 749 0310`). Está confirmado por el cliente en el `config.js` de la landing.

## Activar Google Analytics 4

La tarjeta viene con el **placeholder** `G-XXXXXXXXXX` y **desactivado a propósito**
(mientras el ID sea el placeholder no se carga ningún script, así no se mezclan las
visitas con otra propiedad ni aparecen errores en consola).

1. Entra a https://analytics.google.com/ con la cuenta de Google del cliente.
2. **Admin → Crear propiedad** → nombre: `UneFibra Card`.
3. **Flujo de datos → Web** → URL: `https://konfiozinc.github.io/unefibra-card/`.
4. Copia el **ID de medición** (formato `G-XXXXXXXXXX`).
5. En `index.html`, busca `G-XXXXXXXXXX` y reemplaza **las dos apariciones** por tu ID.
6. `git add -A && git commit -m "Chore: activar GA4 de la tarjeta" && git push`

El seguimiento de conversiones a Firestore (colección `eventos`, proyecto
`konfio-zinc`) ya funciona y **no** necesita configuración: toma el nombre de la
tarjeta de la URL, así que estas visitas quedan separadas de las de Mega Express.

## Paleta (extraída de la landing de UneFibra)

| Uso | Hex |
|---|---|
| Azul de marca (botones, CTA) | `#0060e0` |
| Cian de marca (acentos, badges, títulos) | `#00b0f0` |
| Fondo de página | `#081a3a` |
| Superficie de tarjeta | `#10294f` |
| Fondo suave / tinte | `#0c2248` · `#143059` |
| Texto principal | `#eaf2ff` |
| Texto secundario | `#a6b7d8` |
| Degradado de marca | `linear-gradient(120deg,#00b0f0,#0060e0)` |

Contraste verificado: 11 de los 12 pares cumplen WCAG AA. El único que no es
**texto blanco sobre el verde de WhatsApp (`#25D366`)**, que es el color de marca
de WhatsApp y se mantiene igual que en las demás tarjetas de la agencia.

## Logo

- **Fuente:** `assets/img/logo.webp` del repo de la landing de UneFibra (367×170, con transparencia).
- Variantes con alfa: `assets/logo/logo-200.webp`, `logo-500.webp`, `icons/favicon-32.webp`, `favicon-64.webp`.
- `icons/apple-touch-180.*` y los PNG del manifest van con **fondo blanco** porque iOS y los iconos PWA no manejan bien la transparencia.
- El original que entregó el cliente quedó en `tools/originales/` (excluido de git).

## Pendientes

- [ ] **Activar GitHub Pages** en este repo (Settings → Pages → `main` → `/ (root)`).
- [ ] Crear la propiedad GA4 y pegar el ID (ver arriba).
- [ ] Fotos reales de instalaciones: hoy la galería muestra láminas "Foto pendiente" (`CONFIG.galeria`).
- [ ] Redes sociales: los botones se ocultan solos hasta que haya enlaces reales (`CONFIG.redes`).
- [ ] Dirección exacta: hoy solo "Medellín, Antioquia" (el dato con dirección de la landing está marcado como provisional).

---

Tarjeta desarrollada por [KONFÍO ZINC](https://konfiozinc.github.io/card/).
