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
duracion: "5 días"
viajeros: "Pareja"
presupuesto: "Medio"
portada: imagenes/portada.jpg
resumen: "Miradores, tranvías y pastelerías: Lisboa a pie y sin prisas."
etiquetas: [ciudad, gastronomía, europa]
ultima_revision: 2026-11-25
---
```

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
