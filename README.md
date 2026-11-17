# Verb Trainer

Aprende y practica los verbos en inglés en sus 3 formas. Funciona en el navegador, sin servidor ni dependencias, y guarda tu progreso en tu dispositivo.

**Contenido**

- [Características](#características)
- [Phrasal verbs](#phrasal-verbs)
- [Uso](#uso)
- [Cuándo un verbo está dominado](#cuándo-un-verbo-está-dominado)
- [Audio](#audio)
- [Datos guardados](#datos-guardados)
- [Cómo editar el contenido](#cómo-editar-el-contenido)
- [Archivos](#archivos)

---

## Características

| Sección | Qué hace |
|---|---|
| Estudiar | Tabla de verbos regulares e irregulares (base, past simple, past participle, español) con filtros y búsqueda |
| Mis verbos | Lista personal de 80 verbos con 3ª persona (s/es), pasado, participio y gerundio (-ing) |
| Phrasal verbs | 40 phrasal verbs en 4 categorías, con significado, ejemplo, IPA y audio |
| Practicar | 4 modos de práctica con rondas sin repetidos |
| Tarjetas | Flashcards con filtros y modo mezclar |
| Progreso | Porcentaje de acierto por verbo, racha y récord |
| Audio | Pronunciación en inglés americano e IPA |
| Tema | Modo claro y oscuro automático según el sistema |

### Modos de práctica (verbos)

- `Base → Past / Participle`
- `Español → 3 formas`
- `Completar forma faltante`
- `Past → Base`

---

## Phrasal verbs

40 phrasal verbs organizados en 4 categorías:

| Categoría | Ejemplos |
|---|---|
| Trabajo y estudio | carry out, hand in, figure out, come up with |
| Problemas y soluciones | break down, run out of, put off, call off |
| Comunicación y relaciones | bring up, get along with, speak up, reach out to |
| Vida diaria y desarrollo | look for, give up, keep up with, put up with |

**Lista:** filtra por categoría o busca por phrasal, significado o ejemplo.

**Practicar:**

- `Español → Phrasal verb`: escribes el phrasal en inglés.
- `Phrasal verb → Significado`: eliges entre 4 opciones.

> Nota: al escribir, algunos phrasal aceptan la versión sin la preposición final (por ejemplo, `catch up` para `catch up on`).

---

## Uso

1. Abre `index.html` en tu navegador, o sírvelo desde cualquier hosting estático.
2. Para instalarla como app (PWA), ábrela desde `http://` o `https://`.

> Nota: si abres el archivo directamente (`file://`) la app funciona igual, pero sin modo offline. El service worker solo se registra con `http(s)`.

---

## Cuándo un verbo está dominado

Un verbo cuenta como dominado cuando tiene **al menos 3 intentos** y **80 % o más de aciertos**. Un solo acierto no basta. El mismo criterio aplica a los phrasal verbs.

| Nivel | Criterio |
|---|---|
| Por aprender | Pocos aciertos |
| En progreso | 40 % o más de aciertos |
| Dominado | Cumple el criterio de arriba |

---

## Audio

Usa la API Web Speech del navegador, por lo que la calidad depende de las voces instaladas en tu dispositivo.

- Prefiere voces locales en inglés de EE. UU. de mejor calidad (Natural, Enhanced, Samantha, Aria, etc.).
- Velocidad ajustable en phrasal verbs: Normal, Lento o Rápido.
- Botón "Phrasal + ejemplo" para oír el phrasal y luego la oración completa.
- IPA visible bajo cada verbo y phrasal.

> Nota: si no se oye nada, instala una voz en inglés en los ajustes de texto a voz del sistema.

---

## Datos guardados

Todo se guarda en `localStorage`, solo en tu dispositivo:

| Clave | Contenido |
|---|---|
| `vt_progress` | Aciertos y errores por verbo |
| `vt_phrasal` | Aciertos y errores por phrasal verb |
| `vt_sessions` | Número de sesiones |
| `vt_streak` / `vt_best` | Racha actual y mejor racha |

El botón **Reiniciar progreso** (pestaña Progreso) borra los datos de verbos y phrasal verbs.

---

## Cómo editar el contenido

Todo está en `index.html`:

| Variable | Qué contiene |
|---|---|
| `VERBS` | Base de datos de verbos (regulares e irregulares) |
| `MY_TABLE` | Lista personal: `n\|base\|3ra persona\|past\|participio\|gerundio` |
| `PHRASALS` | Phrasal verbs (`cat`, `en`, `es`, `ex`, y `alt` opcional) |
| `PH_CATS` | Nombres de las categorías de phrasal verbs |
| `PH_IPA` / `IPA_RAW` | Pronunciación fonética de phrasal y verbos |
| `SAY_FIX` | Palabras que el sintetizador pronuncia mal de forma aislada |

**Ejemplo: agregar un phrasal verb**

```js
{ cat:'work', en:'wrap up', es:'terminar / concluir',
  ex:'Let’s wrap up the meeting.' },
```

Y su pronunciación en `PH_IPA`:

```js
'wrap up': 'ræp ʌp',
```

---

## Archivos

```text
verb-trainer/
├── index.html      Aplicación completa (HTML, CSS y JS)
├── manifest.json   Manifiesto PWA
├── sw.js           Service worker (modo offline)
├── icon-192.png    Icono
└── README.md       Este archivo
```

---

Desarrollado por **Emer**.