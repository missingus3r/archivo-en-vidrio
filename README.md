<p align="center">
  <img src="favicon.svg" alt="" width="72" height="72">
</p>

<h1 align="center">Archivo en vidrio — Grabador 5D DIY</h1>

<p align="center">
  Grabar datos dentro de un cubo de vidrio con un láser y leerlos con una cámara.<br>
  <a href="https://tinymoonlabs.com/grabador-5d/">Demo en vivo</a> · <a href="https://tinymoonlabs.com/vidrio.html">Página del proyecto</a> · <a href="https://tinymoonlabs.com">Tiny Moon Labs</a>
</p>

---

> [!NOTE]
> **Es una demo, no un producto.** Es una simulación 3D interactiva y un posible proyecto futuro de
> [Tiny Moon Labs](https://tinymoonlabs.com). No hay máquina construida, nada está a la venta y las
> medidas de la animación están exageradas para que se vean: no es un plano de fabricación.
> Inspirado en [Microsoft Project Silica](https://www.microsoft.com/en-us/research/project/project-silica/);
> no tenemos relación con Microsoft ni con la Universidad de Southampton.

## Qué es

Un láser de pulsos ultracortos enfocado **dentro** de un bloque de vidrio solo lo modifica en el foco.
Ahí deja un punto microscópico, un voxel, que guarda información. El vidrio no necesita energía
para conservar los datos, el agua y los campos magnéticos no lo afectan, y lo que se escribe no se
borra. Esta demo muestra cómo podría ser una máquina casera para grabar y leer esos voxels, con
piezas que se consiguen en Uruguay.

Tiene dos diseños:

| | **5D real** | **3D económico** |
|---|---|---|
| Láser | femtosegundos 1030 nm, con chiller | fibra pulsada 1064 nm (nanosegundos), enfriado por aire |
| Camino del haz | periscopio de 3 espejos | fibra flexible, cabezal atornillado al eje Z |
| Datos por voxel | 3 bits: orientación (2) + retardancia (1) | 1 a 3 bits: presencia, posición en la celda, tamaño |
| Lectura | polarización: analizador giratorio, 4 fotos por zona | campo claro o campo oscuro |
| Medio | cubo de sílice fundida de 20 mm | cubo K9 de 50 mm |
| Costo aproximado | ≈ US$ 52.000 (casi todo es el láser usado) | ≈ US$ 2.300 |

## Qué incluye la demo

- **La máquina en 3D**: pórtico de tres ejes con perfiles 2040, varillas, rodamientos, husillos,
  motores NEMA 17, cabezal óptico, láser, electrónica y cableado. Podés orbitar, hacer zoom, marcar
  cada pieza, aislarla, ver sus etiquetas, abrirla en despiece y comparar los dos diseños.
- **Grabar y leer**: escribís un mensaje y la máquina lo graba voxel a voxel (largo + datos + CRC-8),
  después lo relee con la cámara coaxial y lo valida. Tiene consola G-code, vista del microscopio,
  mapa de voxels por capa y ruido óptico configurable.
- **Partes y precios**: lista completa con tornillería y cables, cantidades tomadas del modelo,
  links y precios en pesos y dólares (relevamiento de octubre de 2026). Elegís entre óptica genérica
  o Thorlabs y tildás lo que ya tenés.
- **Armado y calibración**: el 3D económico se arma desde cero, tornillo a tornillo, en 22 pasos, y
  se calibra en 8 más: homing, escuadra, pasos/mm, cero de foco, alineación láser-cámara, energía,
  posiciones y prueba final.

## Cómo usarla

No hay que instalar ni compilar nada. Abrí `index.html` con doble clic, o entrá a la
[demo en vivo](https://tinymoonlabs.com/grabador-5d/). Funciona mejor en una computadora.

- Arrastrar: orbitar · rueda: zoom · clic derecho: desplazar.
- Clic en una pieza: ficha con precio y link · doble clic: enfocar · **I**: aislar · **F**: enfocar · **Esc**: salir.

## Archivos

| Archivo | Qué hace |
|---|---|
| `index.html` | Página, estilos y pestañas (Operación, Partes y precios, Armado, Cómo funciona). |
| `js/geo.js` | Materiales por pieza, perfil 2040 con ranuras en T, texturas. |
| `js/comp.js` | Cada componente: SK8, SC8UU, husillo, NEMA 17, RAMPS, ópticas, láseres, cámara, etc. |
| `js/machine.js` | El ensamble completo, los dos diseños, el haz, los cables y el movimiento de los ejes. |
| `js/sim.js` | Codificación 5D y 3D (1–3 bits), grabación, validación, lectura y vista del microscopio. |
| `js/assembly.js` | Los 30 pasos de armado y calibración. |
| `js/ui.js` | Selección, aislamiento, etiquetas, lista de partes y totales. |
| `js/bom.js` | Lista de materiales con precios, links y fuentes. |
| `js/main.js` | Escena, luces, cámara y bucle de dibujo. |
| `vendor/` | [Three.js](https://threejs.org) r147 (MIT), sin cambios. |

## Sobre los precios

Son un relevamiento de octubre de 2026 en Uruguay, con dólar BROU a $ 41,25. MercadoLibre pide
iniciar sesión para ver las publicaciones, así que esos precios salen de los resúmenes del buscador:
confirmalos antes de comprar. Los importados no incluyen flete ni impuestos. Los ítems marcados con
≈ son estimados.

## Fuentes

- Microsoft Research — [Project Silica](https://www.microsoft.com/en-us/research/project/project-silica/).
- Anderson, Black, Rowstron y otros — [*Project Silica: Towards Sustainable Cloud Archival Storage in Glass*](https://www.microsoft.com/en-us/research/uploads/prod/2023/09/ProjectSilica-SOSP23.pdf) (SOSP 2023).
- Microsoft Research — [Project Silica's advances in glass storage technology](https://www.microsoft.com/en-us/research/blog/project-silicas-advances-in-glass-storage-technology/) (2026).
- University of Southampton, ORC — [5D data storage](https://www.orc.soton.ac.uk/news/5108) (2016).

## Licencia

[MIT](LICENSE). Three.js, en `vendor/`, tiene su propia licencia MIT.
