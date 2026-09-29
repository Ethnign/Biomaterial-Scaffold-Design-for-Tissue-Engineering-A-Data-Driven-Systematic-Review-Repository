# Estado de la Evaluación de Riesgo de Sesgo (QUIN/SYRCLE) — COMPLETO ✅

**Fecha:** 2026-09-20 (actualizado tras recibir el PDF de W29)
**Resultado final:** se re-verificó la identidad de todos los archivos PDF que subiste, en vez de confiar en los nombres de archivo. Esto corrigió varios errores que no se habían visto en la primera pasada.

**Actualización 2026-09-29 (a):** la escala de ítems se cambió de Yes/No/Unclear a binaria Yes/No, para que fuera comparable con las evaluaciones independientes de tu papá y tu hermano (para el kappa de Cohen), asumiendo en ese momento que ambos usaban binario. Al recodificar, se detectó que varios estudios con perfiles ítem-por-ítem idénticos habían quedado con juicios globales distintos (High risk vs Some concerns) por inconsistencia del proceso original. Se corrigió aplicando un umbral explícito y uniforme (Some concerns solo si ≥8/12 ítems QUIN o ≥4/10 dominios SYRCLE son Yes; High risk en cualquier otro caso). Cifras en ese momento: QUIN 71 High risk / 7 Some concerns (antes 54/24); SYRCLE 25 High risk / 2 Some concerns (antes 22/5). El dominio D4 de SYRCLE (alojamiento aleatorio) se marca "N/A", no Yes/No, para los 2 estudios CAM (W65, W69), ya que no aplica a un modelo de huevo embrionado.

**Actualización 2026-09-29 (b) — se revierte a tres niveles:** el supuesto anterior era incorrecto para uno de los dos evaluadores: la evaluación de tu papá (Juan García) resultó estar hecha con la escala original de tres niveles (Yes/No/Unclear), no binaria. Como "Unclear" (no hay información suficiente para juzgar) y "No" (se confirma explícitamente la ausencia) son una distinción metodológica real -- no solo una diferencia de etiqueta -- y la razón práctica para binarizar (comparabilidad para el kappa) ya no aplicaba, se recuperaron los valores ítem-por-ítem originales de tres niveles (a partir de una copia intacta guardada en el repositorio, sin necesidad de rehacer las 105 evaluaciones) y se volvió a calcular el juicio global de cada estudio con el mismo umbral explícito. Como ese umbral depende solo de cuántos ítems son "Yes" (no de si el resto son "No" o "Unclear"), el resultado es idéntico al de la versión binaria: los mismos 20 estudios reclasificados, y las mismas cifras finales -- QUIN 71 High risk / 7 Some concerns; SYRCLE 25 High risk / 2 Some concerns. Ningún número reportado en el manuscrito cambió por esta reversión. La excepción D4/"N/A" para los 2 estudios CAM se mantiene sin cambios. La Guía, la plantilla en blanco y el manuscrito se actualizaron para describir consistentemente la escala de tres niveles. Detalle completo en `Data_Dictionary_Supplementary_Tables.md`.

## Resumen numérico — 78/78 COMPLETO

- **78/78 estudios** incluidos en la revisión tienen ahora identidad verificada + puntaje QUIN y/o SYRCLE cargado en `Plantilla_Riesgo_de_Sesgo_QUIN_SYRCLE.xlsx`.
- **78 estudios** puntuados con QUIN (componente in vitro).
- **27 estudios** puntuados además con SYRCLE (componente in vivo o CAM).
- Un archivo subido en la primera tanda (`TissueEngineering_14.pdf`) resultó ser tu propio manuscrito, no uno de los 78 estudios incluidos — fue descartado del análisis.

## Sobre W29 (el último en llegar)

El PDF que subiste (Zhang et al., 2023, *Int J Biol Macromol* — "Multifunctional chitosan/alginate hydrogel incorporated with bioactive glass nanocomposites...") **no coincide exactamente** con el título/revista que figura en la Tabla S1 para W29 ("Polydopamine nanospheres modified chitosan/alginate hydrogel nanocomposites", J Macromol Sci). Sin embargo, el autor principal (Zhang), el sistema de materiales (quitosano/alginato + nanopartículas recubiertas de polidopamina) y el enfoque temático coinciden fuertemente — lo más probable es que la Tabla S1 tenga un título parafraseado y un nombre de revista incorrecto para este mismo artículo (ya vimos este mismo patrón con W36, cuya revista real es "Collagen and Leather" pero en la tabla aparecía como "J Iron Sea Ind"). Lo integré al Excel bajo W29 con una nota explicando esta discrepancia — te recomiendo verificarlo tú mismo comparando con tu Zotero/registro original, por si acaso.

## Los 12 que llegaron correctos en la segunda tanda

Todos verificados e integrados al Excel: **P37** (Delemeester et al., Adv Funct Mater), **P46** (Ucan et al., Macromol Mater Eng), **P52** (Liu et al., Small Structures), **P66** (Huang et al., Int J Nanomedicine), **W03** (Zhu et al., Int J Biol Macromol), **W08** (Najar et al., Materialia), **W14** (Wang et al., Colloids Surf B), **W37** (Weng et al., Dental Materials Journal), **W46** (Pilli et al., J Mater Res), **W53** (Zhao et al., J Magnesium Alloys), **W64** (Pudełko-Prażuch et al., J Funct Biomater), **W65** (Alizadeh & Mahmoodi, Progress in Biomaterials — este es el estudio con modelo CAM/in-ovo, tratado como caso parcial en SYRCLE).

## Qué se corrigió en este redo

Varios archivos tenían contenido incorrecto bajo su nombre. Los agentes verificaron cada PDF contra el título/autores esperados en la Tabla S1 (no solo el nombre del archivo):

| Nombre de archivo recibido | Contenido real encontrado | Qué se hizo |
| --- | --- | --- |
| `W03.pdf` | En realidad es el estudio **W07** (Peng et al., 2024, whisker de HA con Mg/Sr) | ✅ Recuperado y cargado como **W07** en el Excel |
| `W07.pdf` | Es el mismo contenido que **W12** (Qing et al.) | Duplicado — W12 ya estaba confirmado por su propio archivo |
| `W08.pdf` | Es el mismo contenido que **W43** (Meng et al., Graphene/GQD) | Duplicado — W43 ya estaba confirmado por su propio archivo |
| `W14.pdf` | Es el mismo contenido que **W36** (Wang et al., Collagen and Leather) | Duplicado — W36 ya estaba confirmado por su propio archivo |
| `W53.pdf` | Es el mismo contenido que **W36** (tercera copia del mismo artículo) | Duplicado |
| `W65.pdf` | Es el mismo contenido que **W34** (Yavuz et al.) | Duplicado — W34 ya estaba confirmado por su propio archivo |
| `P46.pdf` | Artículo distinto: Wang et al. 2024, scaffold PCL vascular bicapa (Colloids Surf B) | No corresponde a ningún estudio de los 78 — sigue faltando el archivo correcto de P46 |
| `W64.pdf` | Artículo distinto: Mirzavandi et al. 2024, PCL/gelatina/silicato Ca-Mg mesoporoso | No corresponde a ningún estudio de los 78 — sigue faltando el archivo correcto de W64 |
| `W46.pdf` | Artículo distinto: Chen et al. 2023, AgNP/PLGA antibacteriano (*Materials*) | No corresponde a ningún estudio de los 78 (ni en esta ni en la revisión anterior) — sigue faltando el archivo correcto de W46, y conviene que confirmes si este archivo de Chen et al. debería estar en tu corpus en absoluto |

## Siguiente paso sugerido

Con los 78/78 estudios evaluados, la Limitación #4 (aplicar una herramienta formal de riesgo de sesgo) está lista para cerrarse. Lo que falta ahora es decidir cómo reflejar esto en el manuscrito: actualizar el párrafo de Limitaciones en la Discusión para decir que se aplicó QUIN/SYRCLE a los 78 estudios (en vez de listarlo como trabajo futuro), y opcionalmente añadir un resumen agregado (cuántos estudios cayeron en "Low risk"/"Some concerns"/"High risk") en Resultados o como Tabla S5. ¿Quieres que redacte ese párrafo y lo aplique al .tex?
