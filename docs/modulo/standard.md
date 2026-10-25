# standard.md: qué tiene que cumplir {{el módulo}}

> **Rol:** normativo sobre un módulo, como una línea de comandos, una API o un formato de archivo.
> Manda sobre el código del módulo; `docs/REQUIREMENTS.md` y `docs/DESIGN.md` mandan sobre él. Su
> par descriptivo es `surface.md`, en esta misma carpeta. **Régimen:** se corrige, y cada cambio
> lleva su decisión. **Origen:** {{fecha y decisión que abrió el módulo}}.

Un módulo tiene carpeta propia solo cuando tiene una superficie que alguien usa desde afuera. Se
crea con permiso del autor, como cualquier documento.

## 1. {{Regla}}

{{Lo que el módulo tiene que cumplir, en una oración comprobable. Si un test la comprueba, el
nombre del test.}}

{{Si el módulo es una línea de comandos, el estándar contesta por lo menos cinco preguntas: qué
código de salida corresponde a cada condición, qué va a stdout y qué a stderr, cómo se piden la
ayuda y la versión, qué test impide que la ayuda y el manual se separen, y de dónde sale cada valor
por defecto que se muestra. Si no lo es, este párrafo se borra.}}

## 2. Lo que este estándar no cubre todavía

{{La lista, para que su ausencia no se lea como permiso.}}
