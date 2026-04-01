# 🚂 Calculadora de Carga Ferroviaria

Herramienta web para el cálculo de carga y planificación de composiciones en el transporte ferroviario de perfiles de acero (carriles).

**[→ Abrir la calculadora](https://tu-usuario.github.io/rail-load-calculator/)**

---

## Descripción

Aplicación de página única (SPA) diseñada para resolver dos problemas habituales en la logística de expediciones de carriles de acero por ferrocarril:

1. **Cálculo de carga** — Dado un peso máximo admitido o un número de unidades, determina cuántas unidades caben en un envío y el peso total resultante.
2. **Planificación de composiciones** — Dado un lote de material pendiente de expedir, calcula cuántas composiciones de tren son necesarias y cómo distribuir la carga entre ellas.

La calculadora incluye una base de datos de **más de 40 perfiles de carril** con su peso lineal (kg/m), cubriendo los formatos más comunes del mercado europeo e internacional.

## Funcionalidades

- **Dos modos de cálculo**: peso máximo → unidades, o unidades → peso total.
- **Planificador de composiciones**: distribución automática de carga en múltiples envíos.
- **Indicador visual de ocupación**: barra de capacidad con código de color (óptimo / subóptimo).
- **Historial de cálculos**: acceso rápido a los últimos 10 cálculos realizados.
- **Copiar al portapapeles**: resumen formateado listo para pegar en emails o mensajes.
- **Modo oscuro automático**: sigue la preferencia del sistema operativo.
- **Responsive**: funciona en móvil, tablet y escritorio.
- **Sin dependencias**: HTML + CSS + JS vanilla, sin frameworks ni librerías externas.
- **Offline-ready**: funciona completamente sin conexión a internet una vez cargada.

## Uso

### Opción 1: GitHub Pages (recomendada)

Accede directamente desde el navegador sin instalar nada:

**https://tu-usuario.github.io/rail-load-calculator/**

### Opción 2: Local

```bash
git clone https://github.com/tu-usuario/rail-load-calculator.git
cd rail-load-calculator
open index.html   # macOS
# o simplemente abre index.html con tu navegador
```

No requiere servidor web, compilación ni dependencias.

## Perfiles incluidos

La calculadora incluye los siguientes formatos de carril con su peso lineal:

| Rango | Ejemplos | Peso (kg/m) |
|-------|----------|-------------|
| Ligeros | CAR200, CAR33C | 19,8 – 33,0 |
| Medios | CAR400 – CAR500 | 39,8 – 50,9 |
| Pesados | CAR54E – CAR60E | 53,8 – 60,6 |
| Extra pesados | CAR65G – CAR76A | 64,9 – 76,2 |

## Capturas

<p align="center">
  <em>La interfaz se adapta automáticamente a modo claro y oscuro.</em>
</p>

## Tecnología

- **HTML5** semántico con atributos ARIA
- **CSS3** con custom properties y `prefers-color-scheme`
- **JavaScript** vanilla (ES6+)
- **Google Fonts** — DM Sans + JetBrains Mono
- Sin frameworks · Sin build tools · Sin dependencias

## Configuración de GitHub Pages

1. Ve a **Settings → Pages** en tu repositorio.
2. En **Source**, selecciona la rama `main` y la carpeta `/ (root)`.
3. Guarda y espera unos segundos. Tu sitio estará disponible en `https://tu-usuario.github.io/nombre-repo/`.

## Personalización

### Añadir nuevos formatos de carril

En el archivo `index.html`, localiza el objeto `FORMATOS` y añade nuevas entradas:

```javascript
const FORMATOS = {
  // ... perfiles existentes ...
  "CAR_NUEVO": 55.00,  // peso en kg/m
};
```

### Cambiar el límite de peso máximo

El límite actual es 300.000 kg (300 t). Para modificarlo, busca las validaciones con `300000` en las funciones `calcular()` y `calcularComp()`.

## Licencia

MIT License — consulta el archivo [LICENSE](LICENSE) para más detalles.

## Autor

**Rubén Prendes**

---

<p align="center">
  <sub>Hecho con 🧡 para la gente de expediciones</sub>
</p>
