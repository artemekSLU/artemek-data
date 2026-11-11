# Datos abiertos de Artemek

**Versión 2026.11.11.2** · 2026-11-11 · Licencia [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) · Fuente: [artemek.com](https://www.artemek.com)

Datos públicos sobre el taller del coche en España que publicamos en artemek.com: precios de taller con sus fuentes, nuestros estudios de datos, los plazos para contestar una hoja de reclamaciones en cada comunidad autónoma y la comparativa de programas de gestión de taller. Son las mismas cifras que salen en la web, con sus mínimos de muestra ya aplicados.

*Open data about car repair in Spain published on artemek.com (workshop prices with their sources, data studies, complaint-reply deadlines per region, workshop software comparison). Spanish column names; CC BY 4.0.*

## Cómo citarlo

> Artemek, «Datos abiertos de Artemek», versión 2026.11.11.2 (2026-11-11). https://www.artemek.com · CC BY 4.0.

El archivo `CITATION.cff` tiene la cita en formato estándar. La licencia pide atribución: nombra a Artemek y enlaza https://www.artemek.com.

## Qué contiene

| Archivo | Filas | Qué es | En la web |
|---|---:|---|---|
| `precios/indice-precios.csv` | 3 | Índice de precios del taller (precios que cada negocio publica en su web) | https://www.artemek.com/indice-precios |
| `precios/estudio-precios-espana.csv` | 12 | Lo que cuestan las reparaciones del coche: cifras de España | https://www.artemek.com/estudios/precios-taller-2026 |
| `precios/estudio-precios-provincias.csv` | 44 | Lo que cuestan las reparaciones del coche: cifras por provincia | https://www.artemek.com/estudios/precios-taller-2026 |
| `precios/mano-obra-comunidades.csv` | 2 | Mano de obra por comunidad autónoma (€/hora, IVA incluido) | https://www.artemek.com/estudios/precios-taller-2026 |
| `estudios/informacion-tecnica-para-talleres-independientes-en-espana-2026/portales.csv` | 45 | Portales oficiales de información técnica por marca | https://www.artemek.com/talleres/recursos/informacion-tecnica-para-talleres-independientes-en-espana-2026 |
| `estudios/informacion-tecnica-para-talleres-independientes-en-espana-2026/acceso.csv` | 8 | Catálogos de tiempos y plataformas de diagnosis por forma de acceso | https://www.artemek.com/talleres/recursos/informacion-tecnica-para-talleres-independientes-en-espana-2026 |
| `estudios/informacion-tecnica-para-talleres-independientes-en-espana-2026/tipos.csv` | 10 | Qué fuentes hemos revisado | https://www.artemek.com/talleres/recursos/informacion-tecnica-para-talleres-independientes-en-espana-2026 |
| `estudios/reclamar-al-taller-plazos-y-hojas-de-reclamaciones-por-comunidad/comunidades.csv` | 19 | El plazo del taller para contestar, por comunidad autónoma | https://www.artemek.com/conductores/recursos/reclamar-al-taller-plazos-y-hojas-de-reclamaciones-por-comunidad |
| `reclamaciones/plazos-por-comunidad.csv` | 20 | Plazo del taller para contestar una hoja de reclamaciones, por comunidad autónoma | https://www.artemek.com/conductores/recursos |
| `comparativa/programas.csv` | 42 | Programas de gestión de taller comparados | https://www.artemek.com/comparativa |
| `comparativa/valores.csv` | 1798 | Lo que la web de cada programa dice, fila a fila | https://www.artemek.com/comparativa |

Cada CSV es UTF-8 con una fila de cabecera (las claves de columna). `datapackage.json` (Frictionless Data Package) y `croissant.json` (MLCommons Croissant 1.0) describen cada columna.

## Método

### Precios de taller (`precios/`)

Datos recogidos hasta el 2026-10-14.

- Cómo los recogimos: en octubre de 2026, agentes de inteligencia artificial buscaron páginas públicas y las descargaron con herramientas automáticas (httpx y un navegador Playwright), respetando robots.txt y sin saltarse ningún bloqueo. De cada precio guardamos el extracto literal, el enlace y la fecha, para que se pueda comprobar. Los comparadores que publican precios de talleres concretos cuentan en la cifra, pero en las fuentes solo mostramos su total, sin nombres de negocios.
- Solo precios publicados: webs de talleres y cadenas, estudios, prensa, comparadores y tarifas oficiales, cada uno con su enlace, la fecha que indica y la fecha en que lo vimos.
- Solo cuentan los precios que dicen si llevan IVA. Los que no lo dicen y los «desde» se quedan fuera de las cifras (se ven en las fuentes, marcados).
- Preferimos los precios de los últimos 36 meses. Si no hay bastantes en ningún sitio, usamos los más antiguos que tengamos, y la cifra dice de qué año es el precio más antiguo que entra.
- Un mismo negocio, estudio o artículo cuenta una sola vez por trabajo y lugar, aunque dé varios precios.
- Damos una cifra solo con al menos 3 precios de al menos 2 webs distintas. Si el municipio no los tiene, usamos la provincia, la comunidad o España, y lo decimos. Si ni España los tiene, no hay cifra.
- La cifra es la mediana. El tramo va del percentil 25 al 75 con 5 o más precios; con menos, del más bajo al más alto. Los precios sin IVA se pasan a con IVA (21 %; IGIC 7 % en Canarias).
- Lo que los conductores cuentan en foros, vídeos y redes que pagaron va aparte: sirve para contrastar, no entra en la cifra.

- `indice-precios.csv`: el tramo de precios que publican los propios negocios en su web, por zona, solo con al menos 1 negocio.
- `estudio-precios-*.csv`: la cifra solo con al menos 3 precios de al menos 2 webs distintas, de los últimos 36 meses. `estudio-precios-provincias.csv` lleva solo las cifras propias de la provincia o de su comunidad; la de España está en `estudio-precios-espana.csv`.

*Precios orientativos con IVA, de fuentes públicas citadas. El precio de tu reparación depende del coche y del taller: pide siempre un presupuesto por escrito.*

### Estudios de datos (`estudios/`)

#### Información técnica para talleres independientes en España (2026)

Página: https://www.artemek.com/talleres/recursos/informacion-tecnica-para-talleres-independientes-en-espana-2026 · edición 2026 · datos a 2026-10-27

Hemos reunido con nuestra herramienta de investigación 1179 fuentes públicas sobre información técnica de reparación (portales de las marcas, catálogos, plataformas, asociaciones, normas y sentencias), cada dato comprobado contra su página. Para las tablas, un modelo leyó cada portal, catálogo y plataforma en categorías fijas (marca, forma de acceso, español, SERMI) y un segundo modelo comprobó cada lectura: 329 lecturas confirmadas, 71 descartadas. La fila de cada marca sale solo de páginas del propio fabricante o de un organismo oficial: 62 lecturas de foros, blogs, tiendas, prensa o copias archivadas no cuentan en ella. Buscamos aparte el portal de cada marca que no lo tenía entre esas fuentes (marcas buscadas: 38; páginas leídas: 112). Los recuentos los hace el código. Páginas leídas entre el 2026-10-20 y el 2026-10-27.

*Límites:* Contamos lo que publican las fuentes que hemos encontrado, no todo el mercado: una marca que no está en la tabla puede tener portal, y una forma de acceso «No consta» puede existir. Las condiciones y los precios cambian: compruébalos en la web de cada marca antes de contratar.

#### Reclamar al taller: plazos y hojas de reclamaciones por comunidad

Página: https://www.artemek.com/conductores/recursos/reclamar-al-taller-plazos-y-hojas-de-reclamaciones-por-comunidad · edición 2026 · datos a 2026-10-26

Hemos leído en los boletines oficiales la norma estatal de consumo y el decreto de hojas de reclamaciones de cada comunidad autónoma y de Ceuta y Melilla, y anotado el plazo que cada una da al taller para contestar. El plazo estatal es de 15 días naturales. Una comunidad marcada «Pendiente» aún no la hemos comprobado en su boletín: allí te damos solo el plazo estatal. Revisamos la tabla cuando cambia una norma.

*Límites:* Es un resumen de lo que dicen las normas, no asesoramiento legal para tu caso. Varias comunidades no ponen plazo al taller: es Consumo quien le pide explicaciones cuando lleva la reclamación.

### Plazos de reclamaciones (`reclamaciones/`)

Hemos leído en los boletines oficiales la norma estatal de consumo y el decreto de hojas de reclamaciones de cada comunidad autónoma y de Ceuta y Melilla. `plazo_dias` es el plazo que la norma da al taller para contestar; vacío cuando la comunidad no le fija plazo o cuando aún no lo hemos comprobado en su boletín (`comprobado` = pendiente: ahí rige el plazo estatal). Comprobadas: 8 de 20. Es un resumen de las normas, no asesoramiento legal.

### Comparativa de programas de taller (`comparativa/`)

Cada valor lo leemos en la web del propio programa (la página está en `fuente`) y lo confirma un segundo lector antes de publicarse; `leido_el` es el día en que se leyó. Un programa sin lectura confirmada en 45 días deja de salir. No incluimos las palabras de cada web (son de sus autores): solo el valor, su fuente y la fecha.

## Lo que nunca va aquí

Ningún dato de un taller concreto ni de sus clientes, ningún dato personal, ninguna cifra por debajo de su mínimo de muestra y ningún dato de catálogos o portales de terceros con licencia (tiempos de reparación, recambios).

## Versiones

Cada versión lleva la fecha en su número (`AAAA.MM.DD`); `CHANGELOG.md` dice qué cambió. Se publica una versión nueva solo cuando cambian los datos.

## Licencia

[Creative Commons Atribución 4.0 Internacional](https://creativecommons.org/licenses/by/4.0/). El texto completo está en `LICENSE`.
