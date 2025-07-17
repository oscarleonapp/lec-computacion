# LEC Computación

Este repositorio contiene el sitio web de **LEC Computación**. El sitio está construido en HTML, CSS y JavaScript estático.

## Estructura del proyecto

- `index.html` página principal del sitio.
- `departamentos/` páginas de destino para cada departamento de Guatemala.
- `assets/` recursos estáticos (imágenes, scripts y hojas de estilo).
- `sitemap.xml` mapa del sitio para buscadores.
- `robots.txt` indicaciones para los robots de los buscadores.

## Mantenimiento del sitio

1. **Edición de contenidos**
   - Actualiza los textos directamente en los archivos `.html` correspondientes.
   - Mantén las etiquetas `meta` como `description`, `keywords`, `canonical` y `title` actualizadas para un buen SEO.
2. **Nuevas páginas**
   - Crea el archivo HTML dentro de la carpeta que corresponda.
   - Añade la nueva ruta al `sitemap.xml` para que los motores de búsqueda la indexen.
3. **Actualización de recursos**
   - Coloca imágenes en `assets/img` y hojas de estilo o scripts en las subcarpetas de `assets`.
   - Optimiza las imágenes (peso y tamaño) antes de agregarlas.
4. **SEO básico**
   - Cada página debe tener un título (`<title>`), descripción y, de ser posible, etiquetas `og:` para redes sociales.
   - Utiliza atributos `alt` en todas las imágenes.
   - Revisa que `robots.txt` y `sitemap.xml` estén en la raíz del proyecto.
5. **Pruebas locales**
   - Abre `index.html` en un navegador para verificar que todo funcione correctamente.

## Generar un nuevo sitemap

Ejecuta el siguiente comando desde la raíz del repositorio para actualizar `sitemap.xml`:

```bash
for f in index.html departamentos/*.html; do \ 
  url="https://leccomputacion.com/${f#./}"; \ 
  echo "  <url><loc>$url</loc></url>"; \ 
done | sed '1i<?xml version="1.0" encoding="UTF-8"?>\n<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">' \ 
| sed '$a</urlset>' > sitemap.xml
```

No olvides añadir la referencia al sitemap en `robots.txt` si cambia su ubicación.

