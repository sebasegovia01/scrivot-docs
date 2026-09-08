# scrivot-docs

Documentación pública de [Scrivot](https://scrivot.cl), publicada en
**[docs.scrivot.cl](https://docs.scrivot.cl)**.

Está construida con [Mintlify](https://mintlify.com): las páginas son archivos `.mdx`
y la navegación se declara a mano en `mint.json`. **Una página que no esté listada ahí
no aparece en el sitio**, aunque el archivo exista.

## Ver los cambios en local

```bash
npm i -g mintlify
mintlify dev
```

Queda en `http://localhost:3000` y recarga al guardar. Si al arrancar se queja de una
página que no encuentra, casi siempre es una ruta de `mint.json` que no coincide con el
archivo: se escribe sin extensión y relativa a la raíz (`widget/instalacion`, no
`./widget/instalacion.mdx`).

## Estructura

```
introduction.mdx      Qué es Scrivot y cómo funciona
quickstart.mdx        Puesta en marcha
planes.mdx            Planes (resumen; el detalle vive en billing/)
widget/               Instalación en el sitio, apariencia, dominios
chatbot/              Intenciones, RAG, idiomas
billing/              Planes, prueba gratuita, límites
logo/                 SVG claro y oscuro
mint.json             Navegación, colores, enlaces
```

## Agregar una página

1. Crea el `.mdx` con su cabecera:

   ```mdx
   ---
   title: Título que se ve en la página
   description: Una línea; sale en buscadores y en la vista previa
   ---
   ```

2. Agrégala al grupo que corresponda en `navigation`, dentro de `mint.json`.
3. Comprueba con `mintlify dev` antes de subir.

## Publicación

`main` es la rama publicada: **el push a `main` es el despliegue**. Mintlify reconstruye
el sitio solo, sin paso aparte.

## Idioma

Todo en español, incluida la interfaz (`"locale": "es"` en `mint.json`). Los términos de
producto se escriben como aparecen en la plataforma —*intenciones*, *workspace*,
*widget*— para que quien lea la documentación con la app abierta encuentre lo mismo en
los dos sitios.

## Relación con el asistente de Scrivot

Esta documentación es también la fuente de la que se alimenta el asistente que atiende
en scrivot.cl. Escribir acá es lo que hace que sepa responder: lo que no esté
documentado, no lo sabe.

Conviene tenerlo presente al redactar. Un párrafo que da por supuesto el contexto de la
página funciona bien para quien está leyendo, y mal para quien recibe ese fragmento
suelto como respuesta en un chat. Cuando una sección puede leerse aislada, se entiende
mejor en ambos lados.
