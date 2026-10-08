# Ultima Underworld: The Stygian Abyss (PlayStation) — Traducción al español

[![Invítame a un café en Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/johanderohan)

Ficha del proyecto, capturas y más traducciones al castellano en **[Parches en Castellano](https://parchesencastellano.com/traducciones/playstation/ultima-underworld)**.

Traducción al **español de España** de la versión japonesa de PlayStation de *Ultima Underworld:
The Stygian Abyss* (ウルティマ・アンダーワールド), el clásico de Blue Sky Productions / Looking Glass
y Origin. Se ha traducido **desde el japonés**, cotejado con el guion
inglés original de Origin.

La versión de PlayStation solo salió en Japón y tiene sus propias escenas de vídeo, criaturas en 3D,
retratos de estilo anime y controles adaptados al mando. Con este parche se puede jugar entera en
castellano.

La traducción se distribuye como **parche**. No incluye el juego: necesitas tu propia copia japonesa
para aplicarlo.

## Estado

Última versión: **[v1.0](../../releases/tag/v1.0)**.

| Parte | Estado |
|---|---|
| Conversaciones con los 92 personajes | 4.888 textos traducidos |
| Objetos, mensajes, libros, pergaminos, lápidas, hechizos, menús y tarjeta de memoria | 1.926 textos traducidos |
| Vídeos con voz (introducción, sueños de Garamon, muertes y final) | 160 subtítulos nuevos en 16 vídeos |
| Gráficos con texto (título, entrada al Abismo, mapa, inventario, teclado, lápidas…) | Traducidos |
| Teclado del nombre | Alfabeto castellano con Ñ y vocales con tilde |
| Caracteres españoles | **á é í ó ú ü ñ Á É Í Ó Ú Ü Ñ ¡ ¿ « »** |
| Revisión durante una partida | Parcial (ver abajo) |

Detalles técnicos:

- Las letras españolas se han añadido a la fuente del juego con el mismo color que el texto
  original. Los nombres largos de personajes y algunas habilidades usan una letra estrecha para
  caber en sus recuadros.
- Los subtítulos se han traducido de lo que **se oye** en japonés: el guion hablado de la versión
  de PlayStation es distinto del texto de PC. Las voces y la música originales se conservan intactas.
- Los objetos se nombran antes que su estado («Hacha, con daños») y los nombres de clase y
  habilidad pasan a mayúsculas con sus tildes.
- Se ha ampliado la memoria reservada a los textos generales para que el castellano quepa sin
  recortes. Es lo que hacía colgarse al juego en combate cuando el texto crecía demasiado.

Se quedan como en el original:

- Los logotipos («Ultima Underworld», Origin, Looking Glass y Electronic Arts).
- Las palabras de magia: runas (An, Bet, Corp…) y mantras (Ra, Summ Ra…).
- Los nombres propios del universo de Ultima, con su grafía inglesa.

### Comprobaciones y trabajo pendiente

Se ha probado en emulador desde una partida nueva:

- Arranque, vídeo de introducción, título, creación del personaje y teclado del nombre.
- Mensajes al mirar y usar objetos, inventario, soltar objetos, hoja de personaje, estado,
  libros y lápidas, mapa, descanso, guardar, cargar y continuar.
- Conversaciones (incluidos el trueque y el arreglo de objetos), combate, magia e identificación.
- Los 16 vídeos con subtítulos y la escena final.

Además, cada construcción comprueba de forma automática que todos los textos caben en su sitio y
en la memoria de la consola, que el código de las conversaciones no cambia y que el audio de los
vídeos es idéntico al original. El parche se ha aplicado sobre la pista japonesa original y el
resultado se ha comparado byte a byte con la imagen probada.

**No se ha jugado una partida completa de principio a fin** ni se ha probado en consola real.
Varias de las pruebas de magia, trueque, vídeos y final se hicieron preparando la situación
directamente en la memoria del emulador, no llegando hasta ella jugando. La traducción y su revisión
se han hecho con asistencia de IA, sin revisores humanos independientes. Si encuentras un error,
abre una incidencia con una captura.

Comportamientos que vienen del juego original y se conservan:

- En el intercambio de las botas con el necrófago, rechazar darle comida cierra la conversación
  sin despedida, como en la versión japonesa.
- La comparación del nombre «Eyesnack» no distingue mayúsculas y admite el comienzo del nombre,
  como en el original.

## Cambios

- **v1.0** (08-10-2026): primera versión.

## Cómo aplicar el parche

1. Descarga el parche `.xdelta` de la sección **[Releases](../../releases)**.
2. Consigue tu copia de **Ultima Underworld: The Stygian Abyss (Japón) (Rev 1)**, SLPS-00742, en
   formato BIN/CUE de cuatro pistas (una de datos y tres de música). Solo se modifica la pista 1.
3. **Comprueba que tu pista 1 es la correcta** antes de nada:

   | | |
   |---|---|
   | Archivo | `Ultima Underworld - The Stygian Abyss (Japan) (Rev 1) (Track 1).bin` |
   | Tamaño | 343.678.944 bytes |
   | MD5 | `714b95aca0623b35bea9348db508918c` |

   ```bash
   md5sum "Ultima Underworld - The Stygian Abyss (Japan) (Rev 1) (Track 1).bin"            # Linux
   md5 "Ultima Underworld - The Stygian Abyss (Japan) (Rev 1) (Track 1).bin"               # macOS
   CertUtil -hashfile "Ultima Underworld - The Stygian Abyss (Japan) (Rev 1) (Track 1).bin" MD5   # Windows
   ```

   Si no coincide, el parche fallará o dará un resultado corrupto. Ojo: la primera edición (sin
   «Rev 1») es distinta.
4. Aplica el parche a la pista 1 con una de estas herramientas:
   - **Windows**: [Delta Patcher](https://github.com/marco-calautti/DeltaPatcher/releases)
   - **Linux / macOS**: `xdelta3 -d -s "pista1-original.bin" Ultima.Underworld.ES.v1.0.xdelta "pista1-es.bin"`
5. Comprueba que el resultado tiene el MD5 **`628105cd9aea3a92fa7de794809692da`** y 343.794.192 bytes
   (es algo más grande que el original).
6. Crea una carpeta nueva y pon en ella:
   - el resultado, **con el mismo nombre que la pista 1 original**
     (`Ultima Underworld - The Stygian Abyss (Japan) (Rev 1) (Track 1).bin`);
   - las pistas 2, 3 y 4 originales y el CUE original, sin cambiarles nada.
7. Carga el CUE en tu emulador y empieza una partida nueva.

Aplica el parche sobre la **pista 1 japonesa original**, no sobre una copia ya parcheada (tampoco
sobre la traducción inglesa).

## Créditos

- [UU_PSX_ENG](https://github.com/gertius1/UU_PSX_ENG), de Gertius, autor de la traducción inglesa de
  esta versión: su documentación y su adaptación del guion de PC han servido de referencia. Este
  parche se ha construido de nuevo desde el original japonés y no reutiliza sus archivos.
- Subtítulos dibujados con la fuente Liberation Sans (licencia SIL Open Font License).
- Herramientas: jPSXdec, xdelta3, Beetle PSX y faster-whisper (transcripción del audio japonés).

## Aviso

Este proyecto es una traducción hecha por afición, sin ánimo de lucro y sin relación alguna con
Electronic Arts, Origin, Looking Glass ni sus sucesores. Aquí no se distribuye el juego ni ninguna
parte de él: solo un parche que modifica una copia que ya tengas.

Si eres el titular de los derechos y quieres que retire esto, abre una incidencia y lo hago.
