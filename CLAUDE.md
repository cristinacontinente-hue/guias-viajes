# Guías de viaje: instrucciones para Claude

Este repositorio es una web de guías de viaje publicada con GitHub Pages (Jekyll).
Quien te escribe **no tiene perfil técnico**: habla con ella en español, sin jerga
(nada de "commit", "branch" o "front matter" sin explicarlo), y encárgate tú de
todos los detalles técnicos.

## Estructura: una carpeta por viaje

Cada viaje vive en su propia carpeta dentro de `viajes/`, con su contenido y sus imágenes:

```
viajes/
  lisboa-2026/
    index.md          ← la guía
    imagenes/
      portada.jpg
      tranvia-28.jpg
      pasteis-de-belem.jpg
  japon-primavera-2027/
    index.md
    imagenes/
      ...
```

- **Nombre de la carpeta**: `destino-año` o `destino-estacion-año`, en minúsculas,
  sin tildes, sin ñ y con guiones. Ejemplos: `lisboa-2026`, `costa-brava-verano-2027`.
- **Cada viaje es independiente**: no compartas imágenes entre carpetas ni enlaces
  a imágenes de otro viaje. Si hace falta la misma foto, cópiala.
- La guía siempre se llama `index.md`, así la dirección queda limpia:
  `/viajes/lisboa-2026/`.

## Formato de cada guía (`index.md`)

Empieza siempre con esta cabecera (es lo que usa la web para listar los viajes en la portada):

```yaml
---
layout: viaje
title: "Lisboa en 5 días"
destino: "Lisboa, Portugal"
fechas: "Mayo 2026"
fecha_viaje: 2026-05-01        # para ordenar los viajes en la portada (más reciente primero)
duracion: "5 días"
viajeros: "Pareja"
presupuesto: "Medio"
portada: imagenes/portada.jpg
resumen: "Miradores, tranvías y pastelerías: Lisboa a pie y sin prisas."
etiquetas: [ciudad, gastronomía, europa]   # se convierten en los filtros de la portada
lo_mejor: ["Atardecer en el mirador de Santa Luzia", "Pastéis de Belém recién hechos", "Perderse por Alfama"]
no_repetiriamos: ["Hacer cola para el tranvía 28 a mediodía"]
ultima_revision: 2026-11-25
---
```

- `presupuesto` es siempre `Bajo`, `Medio` o `Alto` (la web lo muestra como €, €€ o €€€).
- `lo_mejor` y `no_repetiriamos` (3 puntos como máximo cada uno) salen en dos cajas de color
  al principio de la guía. Pídele a ella estos puntos: son su opinión del viaje.
- Usa etiquetas cortas, en minúsculas y repetidas entre viajes (`ciudad`, `playa`, `montaña`,
  `gastronomía`, `con niños`, `europa`…) para que los filtros de la portada sirvan.

Después, el contenido con estas secciones y en este orden (si una no aplica, omítela):

1. **En pocas palabras**: 3-4 frases sobre qué tiene de especial el viaje.
2. **Cuándo ir**: clima, temporada alta/baja, eventos.
3. **Cómo llegar y moverse**: transporte, tarjetas, trucos.
4. **Itinerario día a día**: un apartado `### Día 1: título` por día, con mañana, tarde y noche.
5. **Dónde comer**: sitios concretos, qué pedir y precio orientativo.
6. **Dónde dormir**: zonas recomendadas y, si los hay, alojamientos concretos.
7. **Presupuesto orientativo**: tabla con transporte, alojamiento, comida y actividades.
8. **Consejos prácticos**: reservas, horarios, seguridad, propinas, enchufes, idioma.
9. **Fuentes**: enlaces a las webs oficiales que has consultado.

Tono: cercano, práctico y en primera persona del plural ("os recomendamos", "fuimos a...")
si el viaje es vivido; neutro si es una guía de planificación. Frases cortas, nada de relleno.

## Funciones extra de cada guía (todas opcionales)

Las guías de ejemplo `viajes/ejemplo-lisboa-2026/` y `viajes/ejemplo-asturias-verano-2025/`
usan **todas** las funciones: cópialas como plantilla. Campos extra de la cabecera:

```yaml
ejemplo: true                 # SOLO en guías de ejemplo: muestra un aviso de datos inventados
valoracion: 5                 # nota de 1 a 5 (estrellas)
ideal_para: "Comer bien y andar mucho"
coordenadas: [38.7223, -9.1393]   # punto del viaje en el mapa de la portada
lugares:                          # mapa de la guía, con chinchetas numeradas
  - { nombre: "Torre de Belém", coordenadas: [38.6916, -9.2160], dia: 3 }
gastos:                           # gráfico de barras del presupuesto
  - { concepto: "Alojamiento", icono: "🛏", importe: 320 }
gastos_nota: "por persona, con vuelos desde Madrid"
galeria:                          # cuadrícula de fotos ampliables
  - { archivo: imagenes/tranvia-28.jpg, texto: "El tranvía 28 subiendo por Alfama" }
```

Dentro del texto (`index.md`):

- `{% include mapa.html %}` → mapa con los `lugares` (al principio del itinerario).
- `{% include gastos.html %}` → barras del presupuesto (en "Presupuesto orientativo").
- `{% include galeria.html %}` → galería (sección `## Galería`, justo antes de "Fuentes").
- Cajas de consejo: un párrafo que empiece por `> ` y, en la línea siguiente,
  `{: .truco}` (💡), `{: .ojo}` (⚠️, avisos), `{: .dato}` (📌) o `{: .cita}` (💬).
- Datos sin verificar: `*(por confirmar)*{: .por-confirmar}` (sale resaltado en amarillo).
- Itinerario: empieza cada momento con 🌅 **Mañana:**, ☀️ **Tarde:**, 🌙 **Noche:**.
- Lista "Qué llevar" con casillas: `- [x] Chubasquero` / `- [ ] Paraguas`.
- Las fotos dentro del texto se amplían al pulsarlas.

Se generan solos, sin hacer nada: tiempo de lectura, botones de compartir e imprimir/PDF,
"Otros viajes" al final, botón de volver arriba, cifras de la portada (viajes, países, días),
el buscador y el mapa de la portada.

Las coordenadas se sacan de OpenStreetMap o Google Maps (clic derecho en el sitio).

## Diseño de la web

- La web se llama **Viajes Continente** ("Un placer para tu mente"). Colores del logo:
  azul marino `#2d2a6b`, naranja `#d4451a` y fondo crema `#fcf0dd`.
- El logo va en `assets/` con un nombre que empiece por `logo` (por ejemplo `assets/logo.png`):
  la web lo detecta y lo pone sola en la cabecera y en la portada.
- La ficha resumen, el índice de secciones y la línea de tiempo del itinerario se generan
  solos a partir de la cabecera y de los títulos `## ` y `### Día N: ...`.

## Imágenes

- Van **siempre** en la carpeta `imagenes/` del propio viaje.
- Enlázalas con rutas relativas: `![Tranvía 28 subiendo por Alfama](imagenes/tranvia-28.jpg)`.
- Renombra las fotos que te pasen con nombres descriptivos en minúsculas y con guiones
  (`IMG_4821.JPG` → `mirador-santa-luzia.jpg`).
- Si alguna pesa más de ~500 KB, redúcela (ancho máximo 1600 px) antes de guardarla.
- Escribe siempre un texto alternativo que describa la foto.
- Usa **solo fotos que te pase ella**. No descargues imágenes de internet: casi
  todas tienen derechos de autor. Si falta alguna, díselo y deja un hueco comentado
  (`<!-- FOTO: mirador al atardecer -->`).
- La imagen de portada se llama siempre `portada.jpg`.

## Antes de escribir una guía nueva

Si no te lo ha dicho ya, pregúntale (en un solo mensaje, de forma breve):
destino, fechas o época, duración, quién viaja, presupuesto, intereses y si es un viaje
ya hecho (con experiencias propias) o uno por planificar.

## Datos fiables

- **Comprueba con búsqueda web** todo lo que cambia con el tiempo: precios, horarios,
  si un restaurante o museo sigue abierto, requisitos de entrada al país.
- Prioriza webs oficiales (turismo, museos, transporte) y añádelas a "Fuentes".
- Si no has podido verificar algo, márcalo como "(por confirmar)" en lugar de inventarlo.
- Actualiza `ultima_revision` cada vez que modifiques una guía.

## Qué puedes tocar y qué no

- ✅ Crear y editar carpetas dentro de `viajes/`.
- ✅ Al editar un viaje, toca **solo** su carpeta.
- ❌ No modifiques `_config.yml`, `_layouts/`, `_includes/`, `assets/` ni la portada
  (`index.md` de la raíz) salvo que te lo pida expresamente. La portada se actualiza
  sola con los viajes nuevos.
- ❌ No borres ningún viaje ni ninguna imagen sin confirmarlo antes con ella.

## Cómo publicar los cambios

Ella ha pedido trabajar **directamente en `main`, sin pull requests**.

1. Haz los cambios y guárdalos directamente en la rama `main` (commit + push a `main`).
2. La web se publica sola en un par de minutos (GitHub Actions → GitHub Pages).
3. Dile en el chat, sin tecnicismos, qué has publicado y el enlace para verlo:
   `https://cristinacontinente-hue.github.io/guias-viajes/` (o la página del viaje).
4. Si pide cambios, hazlos también directamente en `main`.

## Al terminar

Resume en 2-3 líneas qué has creado o cambiado, qué datos quedaron "por confirmar"
y qué fotos faltan, si falta alguna.
