# Vimium para Lupa

Distribución desempaquetada de Vimium 2.4.2 para usar con Lupa. Navegación de teclado, hints, búsqueda y gestión de pestañas.

Versión de la extensión: **2.4.2**. Manifest V3, JavaScript sin paso de compilación.

## Instalar en Chromium

```sh
git clone https://github.com/bunxdev/lupa_extension_vimium.git
```

Abre `chrome://extensions`, activa el modo desarrollador y carga la carpeta del repositorio como extensión desempaquetada.

## Instalar en Lupa

En Lupa 0.0.3 con Compose slim, clona este repositorio en `deploy/slim/.runtime/extensions/vimium/` de tu instalación. En el Compose tradicional, usa `extensions/vimium/`. El archivo debe quedar en `/extensions/vimium/manifest.json` dentro del contenedor.

Lupa descubre los manifiestos al abrir un contexto de Chromium. Reabre el contexto en un momento apropiado, guardando antes el trabajo de la sesión. La descarga del repositorio no modifica las pestañas que ya están abiertas.

## Permisos y límites

- Permisos: `tabs`, `bookmarks`, `history`, `storage`, `sessions`, `notifications`, `scripting`, `favicon`, `webNavigation`, `search`.
- Acceso a sitios: `<all_urls>`.

Las páginas internas y la tienda de extensiones restringen content scripts. La sesión del usuario reportó intermitencias en algunos atajos; no se atribuyen como hecho a MV3. Consulta las evidencias y límites enlazados.

## Procedencia

Consulta [PROVENANCE.md](PROVENANCE.md). Esta publicación conserva el código instalado y añade documentación de distribución; no representa una batería nueva de pruebas contra sitios externos.

## Autoría y mapa de teclas

Proyecto original: [philc/vimium](https://github.com/philc/vimium/tree/v2.4.2), autores y colaboradores de Vimium. Esta copia no es una creación original de Lupa ni implica afiliación con el proyecto. Se conserva la licencia MIT en [MIT-LICENSE.txt](MIT-LICENSE.txt).

| Teclas | Acción |
|---|---|
| `j`, `k` | Bajar/subir |
| `gg`, `G` | Inicio/final de página |
| `J`, `K` | Pestaña anterior/siguiente |
| `g0`, `g$` | Primera/última pestaña |
| `yy`, `yf` | Copiar URL/enlace elegido |
| `i`, `Escape` | Entrar/salir del modo inserción |

[Skill y pruebas verificadas](https://github.com/bunxdev/skillslupa/tree/main/vimium). En el fixture de Lupa 0.0.3-rc.1, `j` funcionó por API y X11 aunque el listener de la página no registró el evento. La API sigue su pestaña gestionada; X11 usa el foco real.
