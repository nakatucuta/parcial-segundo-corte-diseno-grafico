# Parcial Segundo Corte — Fundamentos de Diseño Gráfico

**Docente:** Juan Camilo Suárez Cantero · **Duración:** 1 hora (60 minutos) · **Nota máxima:** 5.0 (5 puntos de 1.0)

Lea esta guía completa **antes de empezar**. Aquí se explica qué pide cada punto y cómo se califica. No contiene las respuestas: cada modelo tiene datos distintos y usted debe sacarlos de **su** enunciado y de **su** boceto.

---

## 1. Antes de empezar

1. El docente le dice qué **modelo** le tocó (del 01 al 10).
2. Entre a la carpeta `Modelo_XX_...` de su modelo y descargue los dos archivos:
   - `enunciado_modelo_XX.pdf`: el examen, con el **boceto** (la imagen del panel que debe construir).
   - `plantilla_modelo_XX.html`: el archivo donde va a programar. Ya trae Bootstrap enlazado, comentarios que indican dónde va cada punto y la sección de la bitácora.
3. Ábralo en VS Code y véalo en el navegador mientras trabaja. Necesita **internet**, porque Bootstrap y las fotos se cargan en línea.

> Para descargar todo junto: botón verde **Code → Download ZIP**.

## 2. Cómo leer el boceto

El boceto es una **imagen** del panel terminado. Tiene letras amarillas que marcan zonas:

| Zona | Qué es |
|---|---|
| **A** | La barra superior (navbar) |
| **B** | El menú lateral (sidebar) |
| **C** | El título principal. La nota amarilla dice su tamaño, su transformación y su espaciado entre letras |
| **D** | Las tarjetas (cards). La nota amarilla dice el borde y el radio |
| **E** | La "Foto del día" (imagen aleatoria) |

En el boceto, la navbar y la sidebar se ven **grises** a propósito: el color real lo calcula usted en el Punto 1. Los números de las cards aparecen como **?** porque usted los debe calcular contando la tabla.

⚠️ Hay datos que **solo están en el boceto**, como las filas de la tabla, los estados y las medidas de las notas C y D. Si usa IA, ella **no ve el boceto** a menos que usted se lo describa bien.

---

## 3. Los 5 puntos

### Punto 1 · Color y tipografía (1.0)
- **Color:** el enunciado le da una fórmula para calcular el **matiz H** a partir del **último dígito de su código estudiantil**. Con ese H arma los colores `hsl(H, S%, L%)` de la navbar y de la sidebar (el enunciado le da los porcentajes). Cada estudiante tiene un color distinto. **Escriba el cálculo como comentario** en el CSS.
- **Tipografía:** el título `<h2 id="titulo">` debe tener el tamaño, la transformación (`text-transform`) y el espaciado (`letter-spacing`) de la nota **C**. Escriba el texto **normal**, tal como aparece en el enunciado: la transformación (mayúsculas, iniciales en mayúscula…) la hace el CSS, no usted.
- Los números de las cards usan las clases de Bootstrap que indica el enunciado.

### Punto 2 · Modelo de caja y layout con Bootstrap (1.0)
- **Ancho de las cards:** el enunciado dice cuánto debe medir cada card **en total** (por ejemplo, "X px × número de filas con cierto estado"). Para saberlo, **cuente en la tabla del boceto**.
- Luego debe escribir el `width` correcto según el `box-sizing` que le pidan. Recuerde lo visto en clase: con `content-box`, el padding y el borde **se suman por fuera** del width; con `border-box`, **quedan por dentro**. Deje el cálculo como comentario.
- **Grid:** Bootstrap divide el ancho en **12 columnas**. El enunciado le dice cuántas columnas ocupa la sidebar (sale de contar filas de la tabla). El contenido ocupa las que faltan para llegar a 12.
- **Tabla:** cópiela del boceto en el mismo orden, con un `badge` del color de cada estado.
- **Cards:** cambie cada **?** por el número real que contó en la tabla. Cada card lleva el mismo color de Bootstrap que su estado.

### Punto 3 · Eventos de clic en JavaScript (1.0)
Se trabaja igual que en clase: `document.getElementById(...)` para encontrar el elemento y `addEventListener('click', function () { ... })` para reaccionar al clic. Su enunciado pide **tres** cosas:
1. Un clic que **cambia algo de la página** (según su modelo, el texto del título o el color de fondo de la navbar).
2. Un clic en el botón principal que muestra un **mensaje** con `alert`.
3. Un **contador**: cada clic sobre el número de una card le suma una cantidad. Use `parseInt`, porque `textContent` devuelve **texto**, no número.

### Punto 4 · Eventos de mouse e imagen aleatoria (1.0)
1. **`mouseenter` y `mouseleave`:** cuando el mouse entra a un elemento, cambia de color; cuando sale, vuelve como estaba.
2. **`dblclick`:** el doble clic sobre la tabla hace algo (mostrar un mensaje o cambiar el título, según su modelo).
3. **Foto del día:** al cargar la página se muestra una foto **elegida al azar** de la lista de 5 direcciones que trae su enunciado (`Math.random` + `Math.floor`, como en la clase 02). En algunos modelos, además, un botón **"Otra foto"** vuelve a elegir una al azar.

### Punto 5 · Bitácora de IA y sustentación (1.0)
**a) Bitácora (0.4).** Al final de la plantilla está la sección `id="bitacora"`. Complétela con **sus propias palabras**:
- Los **3 prompts** más importantes que le escribió a la IA, copiados tal cual. Si no usó IA, escriba "no usé IA" y cómo lo resolvió.
- **Un error** que cometió la IA (o usted) y cómo lo corrigió.
- Una explicación de **mínimo 4 líneas** de cómo funciona su contador y por qué escribió ese `width` en las cards.

**b) Sustentación relámpago (0.6).** Cuando termine, **levante la mano**. El docente abre su archivo y lanza una moneda para escoger **una pregunta**:
- La pregunta le pide **explicar** una parte de su código.
- Y le pide **hacer un cambio en vivo**, usted mismo, en 2 o 3 minutos.

⚠️ **Si no puede explicar ni modificar su propio código, los puntos 3 y 4 se califican sobre el 50 %.**

---

## 4. Reglas importantes

- ✅ **Se permite usar IA** (ChatGPT, Gemini, Copilot…), pero debe **entender** lo que entrega: eso se evalúa en el Punto 5.
- ✅ Use **exactamente los `id`** que pide el enunciado (`navbar`, `titulo`, `btnNuevo`, `num1`/`num2`/`num3`, `tabla`, `foto`…). El docente los usa para revisar.
- ❌ No se permite compartir código ni archivos con compañeros. Cada modelo tiene datos distintos, así que copiar a otro no sirve.
- 📤 **Entrega:** un único archivo `.html` con el nombre `apellido_nombre_modeloXX.html` (por ejemplo, `perez_ana_modelo04.html`).

## 5. Cómo se reparte la nota

| Punto | Tema | Valor |
|---|---|---|
| 1 | Color y tipografía | 1.0 |
| 2 | Modelo de caja y layout | 1.0 |
| 3 | Eventos de clic | 1.0 |
| 4 | Mouse, doble clic e imagen aleatoria | 1.0 |
| 5 | Bitácora (0.4) + sustentación (0.6) | 1.0 |
| | **Total** | **5.0** |

## 6. Preguntas frecuentes

- **¿Qué es "el último dígito de mi código"?** El último número de su código estudiantil. Si su código es 1242520009, su último dígito es **9**.
- **¿Puedo cambiar el diseño?** No. Debe parecerse al boceto: mismas zonas, mismos datos y mismo orden. Solo los colores de la navbar y la sidebar dependen de su código.
- **¿La foto no carga?** Revise que tenga internet y que la imagen tenga `id="foto"`.
- **¿El contador pega los números ("41" en vez de 5)?** Le falta convertir el texto a número.
- **¿Algo no funciona y no sé por qué?** Abra la consola del navegador (**F12 → Console**): ahí aparece el error y la línea donde está.
- **¿Tengo una duda del enunciado?** Pregúntele al docente durante el examen.

Éxitos 🍀
