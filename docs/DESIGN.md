# DESIGN.md: cómo se escribe el código

> **Rol:** normativo sobre el código. Cada principio dice cómo se escribe el código y por qué. Manda
> sobre el código; `docs/REQUIREMENTS.md` manda sobre él. Describe reglas; el estado, qué rutas,
> recursos o funciones existen hoy, va en `docs/ARCHITECTURE.md`. **Régimen:** se corrige, y un
> principio nuevo o cambiado lleva su decisión. **Origen:** plantilla 1.2, sembrada el {{fecha}}
> (`docs/DECISIONS.md`, {{fecha}} "Se adopta la plantilla 1.2").

Un cambio que rompe un principio de acá se rechaza, lo haya escrito una persona o un modelo. Ante la
duda, se copia la forma del código que ya existe en vez de inventar un idioma nuevo.

## 1. {{Principio}}

{{La regla, en una oración que se pueda comprobar. Después, por qué existe: el caso que la hizo
necesaria, con su número si lo tiene. Si se puede comprobar con un comando, el comando.}}

## 2. Los tests

{{Cómo se escriben y se corren los tests. Una suite que alguna vez falló de forma intermitente se
corre N veces, no una, y se queda en esa lista después del arreglo.}}

## 3. Presentación y registro

{{Qué imprime el programa, dónde, y con qué detalle según quién lo invoca: una persona en una
terminal espera una línea de inicio y otra de fin, y un atajo de teclado o una tarea programada
pueden fallar en silencio. Si imprime en una terminal, el principio dice a qué stream va cada cosa,
cuándo lleva color y cómo se apaga, por ejemplo con `NO_COLOR` (https://no-color.org), y cómo se
asegura que un archivo de registro no reciba secuencias de escape. Qué se registra y qué no. Si el
producto tiene interfaz, sus reglas de iconos y colores van acá, no en `CLAUDE.md`.}}

## 4. Los comentarios

**Regla:** un comentario que protege una línea dice qué se rompe sin ella, para que nadie la borre
sin reproducir ese fallo antes. Un comentario que afirma algo del código es una afirmación como
cualquier otra, y cambia en el mismo commit que el código que describe.

**Por qué:** las dos salen de comparar los scripts y los repos del autor el 2026-10-20. La primera
ya era la costumbre de los que más se habían roto, donde la línea que evita un fallo traía un
comentario que lo nombraba. {{Un comentario de este repo que cumpla esa regla, como ejemplo, o se
borra esta oración si todavía no hay código.}}

La segunda responde a un comentario que afirmó durante meses lo contrario de lo que hacía el código
de abajo.

**Dónde está escrito:** el idioma y la voz de un comentario están en `CLAUDE.md`, sección 9.

**Cómo se comprueba:** a mano, en cada PR que toca código. Quien cambia una línea lee los
comentarios que tiene encima, porque ninguna herramienta los revisa.

## 5. Sin escribir todavía

{{Las convenciones que se sabe que hacen falta y nadie decidió. Mientras esta sección tenga algo,
el archivo es una semilla y lo dice.}}
