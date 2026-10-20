# PLANTILLA.md: cómo usar la plantilla 1.2

Este archivo no se copia al repo nuevo. Explica la plantilla, cómo se aplica y qué cambió desde la
versión anterior.

## 1. Qué es

Diez documentos genéricos, más un par opcional para un módulo y un `tests/README.md`. Salen de las
reglas que rigen en MIDI-Scale-Trainer, TL-FCCU y sloprush. La 1.1 corrigió lo que mostró sloprush,
el primer repo que usó la 1.0, y la 1.2 suma lo que dejó la comparación del 2026-10-20 entre los
scripts y los repos del autor.

```
AGENTS.md                  puerta, no manda
CLAUDE.md                  método, jerarquía y formato común
CHANGELOG.md               historia: qué y cuándo
docs/REQUIREMENTS.md       normativo: qué tiene que ser verdad
docs/DESIGN.md             normativo: cómo se escribe el código
docs/ARCHITECTURE.md       descriptivo: qué es el código hoy, y los huecos
docs/GLOSSARY.md           descriptivo: qué significa cada palabra
docs/ROADMAP.md            plan: fases y Backlog
docs/DECISIONS.md          historia: por qué, append-only
docs/TEMPORARY-CONTEXT.md  tránsito: lo que se perdería
docs/modulo/               opcional, solo si hay un módulo con superficie propia
tests/README.md            opcional, solo esa carpeta
```

## 2. Cómo se aplica

1. **Se copia el contenido de la carpeta `plantilla-1.2/`, no la carpeta.** `AGENTS.md`, `CLAUDE.md`
   y `CHANGELOG.md` quedan en la raíz del repo, y el resto en su `docs/` y su `tests/`. Ningún
   documento queda duplicado entre la raíz y `docs/`.
2. **No se copia este archivo.**
3. **`docs/modulo/` se copia solo si el proyecto ya tiene un módulo** con una superficie que alguien
   usa desde afuera: una línea de comandos, una API, un formato de archivo. Entonces la carpeta se
   renombra con el nombre del módulo. Si no lo tiene, no se copia; se agrega el día que aparezca,
   con permiso del autor.
4. **Cada hueco `{{…}}` se reemplaza.** Lo que todavía no se sabe se escribe como texto en la
   sección "Sin escribir todavía" del archivo, nunca como un hueco que queda. Al terminar,
   `grep -rn '{{' --include='*.md' .` tiene que devolver cero.
5. **Si el repo se escribe en inglés**, se traduce el contenido y se cambia la lista de la regla 1
   de prosa. Los nombres de archivo ya están en inglés.
6. **Las líneas base de prosa se miden en el mismo PR**, con el bloque de comandos de `CLAUDE.md`,
   sección 9, y se escriben ahí con su fecha. Se miden después del paso 4: un hueco sin llenar
   cuenta como texto y falsea la medición.
7. **El primer PR es `doc`** y abre la sección `v0.1` del CHANGELOG.

## 3. Qué cambió desde la 1.1

Todo sale del 2026-10-20, salvo el punto 4, que es del 2026-10-02.

1. **`docs/DESIGN.md` gana el principio 4, "Los comentarios",** y "Sin escribir todavía" pasa a ser
   el 5. Un comentario que protege una línea dice qué se rompe sin ella, y uno que afirma algo del
   código cambia en el mismo commit que ese código. El autor pidió las dos reglas para todos sus
   repos, y ya rigen en los tres; ver la tabla de la sección 5.
2. **"Presentación y registro" pregunta más.** El hueco ahora pide el detalle según quién invoca el
   programa, a qué stream va cada cosa, cuándo hay color y cómo se apaga, y que el registro no
   lleve secuencias de escape. Son las diferencias que más se repitieron entre los scripts.
3. **El estándar de un módulo trae las preguntas mínimas de una línea de comandos:** códigos de
   salida, streams, ayuda y versión, opciones documentadas con un test que las sincronice, y
   valores por defecto impresos desde su variable. Salen de `docs/cli/cli-standard.md` de TL-FCCU.
4. **Las citas textuales del autor no cuentan para las reglas 1 y 2 de prosa,** con la función
   `sincitas` en los comandos y la línea "cita textual" en el glosario. Lo decidió sloprush el
   2026-10-02, después de sembrarse: una cita no se reescribe y subía dos líneas base sin prosa
   nueva.
5. **`CLAUDE.md`, sección 9, dice que el piso mide los `.md`** y que los comentarios se revisan a
   mano. Los tres repos decían "docs y comentarios" y ninguno medía comentarios.
6. **`CLAUDE.md`, sección 6, avisa cómo se prueba la versión mostrada:** el test pide que tenga su
   sección en el CHANGELOG. Pedir la de arriba falla después de cada PR doc-only.
7. **El Origen de `CLAUDE.md` dice tres repos**, porque sloprush ya aportó reglas.

## 4. Qué cambió de la 1.0 a la 1.1

Los tres cambios salen de sembrar sloprush, el primer repo que usó la 1.0, el 2026-10-01.

1. **El glosario numera sus grupos.** La 1.0 abría `## Método` sin número y la regla 3 de formato
   pide numerar las secciones de un documento descriptivo. sloprush lo numeró por su cuenta. Ahora
   la plantilla trae `## 1. Método`.
2. **Los pasos de esta guía son explícitos.** Con la 1.0, sloprush terminó con copias de los
   documentos en la raíz y en `docs/`, y con este archivo commiteado, y los dos se borraron en el
   mismo PR de siembra. También quedó `docs/modulo/` con los huecos sin llenar, porque la guía no
   decía que era opcional.
3. **Los huecos se escriben `{{…}}`.** En la 1.0 eran `<…>`, igual que los tokens de formato de
   `CLAUDE.md`, como `<tipo>`, así que un grep no los separaba. Ahora la regla 9 de formato pide
   cero `{{` en un repo sembrado, y "Sin escribir todavía" se suma a `docs/DESIGN.md`.

Además, el **Origen** de cada bloque ya trae la forma que sloprush eligió: "plantilla 1.1, sembrada
el {{fecha}}", con la entrada de `docs/DECISIONS.md` que lo explica.

## 5. Qué la separa de los repos actuales

| Punto | MIDI | FCCU | sloprush | Plantilla 1.2 |
|---|---|---|---|---|
| Línea 1 y bloque Rol, Régimen, Origen | sí | sí | sí | sí |
| Jerarquía | niveles, en `AGENTS.md` | tipos, en `CLAUDE.md` | tipos, en `CLAUDE.md` | tipos, en `CLAUDE.md` |
| Convenciones del código | en `CLAUDE.md`, por decisión | `docs/DESIGN.md` | `docs/DESIGN.md` | `docs/DESIGN.md` |
| Encabezado de decisión | dos puntos en las nuevas | dos puntos | dos puntos | dos puntos |
| Nombres de archivo | mezcla | inglés | inglés | inglés |
| Huecos `{{…}}` | no aplica | no aplica | usa `<…>` de la 1.0 | `{{…}}` |
| Reglas de comentarios | `CLAUDE.md`, "Comentarios" | `docs/DESIGN.md`, principio 12 | `docs/DESIGN.md`, principio 11 | `docs/DESIGN.md`, principio 4 |
| Citas fuera de las reglas 1 y 2 | no | no | sí | sí |

MIDI no cambia de nombres de archivo ni crea `DESIGN.md`: las dos cosas están decididas en ese repo.

## 6. Qué no está verificado

Ni la 1.1 ni la 1.2 sembraron un repo todavía. Las reglas de comentarios ya rigen en los tres
repos; lo que no se probó es la plantilla como semilla, y eso se sabe con el próximo repo.
