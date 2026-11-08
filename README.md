# Fundamentos de Economía

Material de consulta y de trabajo del curso Fundamentos de Economía (código 1035205), Pregrado en Ciencia Política, Facultad de Derecho y Ciencias Políticas, Universidad de Antioquia.

Realizado por Emilio Henao (@elnostos) con Claude (Opus 5.5).

## Contenido

| Archivo | Qué es |
|---|---|
| `index.html` | Portada con enlaces a todas las herramientas |
| `pensamiento.html` | Atlas del pensamiento económico: línea de tiempo, escuelas, autores, temas, casos de hoy, conceptos, laboratorio, repaso y bibliografía |
| `pobreza.html` | Atlas de la pobreza y la desigualdad: dos siglos de datos del mundo, mapa, Colombia por departamentos y La calle |
| `juegos.html` | Economía en el salón: diez juegos experimentales adaptados a Colombia, con tablero para el profesor y vista de celular |
| `docentes.html` | Guía para docentes: cada sección y cada juego explicados paso a paso |

Son páginas estáticas, cada una en un solo archivo. No hay servidor, base de datos ni proceso de compilación.

## Publicar con GitHub Pages

1. Cree un repositorio y suba todos los archivos de esta carpeta a la raíz, incluido `.nojekyll`.
2. En el repositorio, vaya a **Settings → Pages**.
3. En **Build and deployment**, elija **Deploy from a branch**, la rama `main` y la carpeta `/ (root)`.
4. Guarde. En unos minutos el sitio queda en `https://<usuario>.github.io/<repositorio>/`.

Los enlaces entre páginas son relativos, así que el sitio funciona en cualquier dirección.

## Clave del modo profesor

El tablero de los juegos pide una clave. La página solo guarda su huella SHA-256, en la constante `PASS_HASH` de `juegos.html`. Es una barrera para que los estudiantes no abran el tablero por accidente, no un sistema de seguridad: cualquiera que lea el código puede saltársela.

Para cambiar la clave, calcule la huella de la nueva y reemplace el valor de `PASS_HASH`:

```
printf '%s' 'NuevaClave' | shasum -a 256
```

## Datos y almacenamiento

Los resultados de los juegos, el avance del repaso y las preferencias se guardan en el navegador de cada equipo (`localStorage` y `sessionStorage`). Nada se envía a un servidor.

Dependencias externas que se cargan al abrir las páginas:

* Fuentes tipográficas de Google Fonts.
* Retratos de los autores desde Wikipedia, en el atlas del pensamiento.

Los datos del atlas de la pobreza ya vienen incluidos en el archivo: Gapminder, DANE (pobreza monetaria y Encuesta de Calidad de Vida 2024), OMS y Unicef (JMP) y UIT. Los mapas son de Natural Earth.

## Fuentes

Cada juego cita al final de su página de reglas los experimentos originales de los que se adapta. Cada atlas indica sus fuentes de datos y de contenido.

## Licencia

El repositorio no trae licencia todavía. Si quiere que otros docentes reutilicen el material, conviene agregar una antes de publicarlo.
