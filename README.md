# Proyecto: Generación de Energía Piezoeléctrica en Estaciones de Metro

## 📋 Descripción

Este repositorio contiene la documentación completa de la formulación del proyecto para la implementación de sistemas de generación de energía mediante tecnología piezoeléctrica en estaciones del sistema de Metro. El objetivo es aprovechar la energía cinética generada por el tránsito de pasajeros para producir electricidad, contribuyendo a la sostenibilidad y eficiencia energética del sistema de transporte público.

## 🏗️ Estructura del Proyecto (versión concisa y alineada a la metodología)

El proyecto mantiene una organización modular; a continuación se muestra la estructura recomendada, más concisa y alineada con el módulo de formulación:

```
formulacion-proyectos_piezo-electrico-metro/
│
├── main.tex                          # Documento principal (punto de entrada)
│
├── config/                           # Configuración del documento
│   ├── packages.tex                  # Paquetes LaTeX utilizados
│   ├── format.tex                    # Formato del documento (estilos, colores)
│   └── commands.tex                  # Comandos personalizados
│
├── chapters/                         # Capítulos del documento (concisos)
│   ├── 00_resumen_ejecutivo.tex
│   ├── 01_contexto_y_diagnostico.tex
│   ├── 02_objetivos_alcance.tex
│   ├── 03_marco_teorico_metodologia.tex
│   ├── 04_propuesta_tecnica.tex
│   ├── 05_analisis_mercado_y_economico.tex
│   ├── 06_impacto_ambiental_y_social.tex
│   ├── 07_plan_implementacion_y_monitoreo.tex
│   ├── 08_gestion_riesgos_y_dofa.tex
│   ├── 09_conclusiones.tex
│   └── anexos.tex
│
├── sections/                         # Secciones modulares y anexos
│   ├── 01_antecedentes.tex
│   ├── 02_objetivo_general.tex
│   ├── 03_fundamentos_piezoelectricidad.tex
│   ├── anexo_glosario.tex
│   └── anexo_acronimos.tex
│
├── figures/                          # Imágenes y figuras
│   └── (colocar aquí archivos .png, .jpg, .pdf)
│
├── tables/                           # Tablas externas (opcional)
│   └── (colocar aquí archivos .tex de tablas complejas)
│
├── references/                       # Referencias bibliográficas
│   └── bibliography.bib              # Base de datos bibliográfica
│
└── README.md                         # Este archivo

```

## 🎯 Contenido del Documento

### Capítulos principales (resumido y ordenado)

1. **Resumen Ejecutivo**: Síntesis del proyecto, objetivos, beneficios e indicadores clave
2. **Contexto y Diagnóstico**: Antecedentes y diagnóstico del sistema de metro
3. **Objetivos y Alcance**n+4. **Marco Teórico y Metodología**: Metodología aplicada para estudios técnicos y económicos
5. **Propuesta Técnica**: Diseño del sistema y especificaciones
6. **Análisis de Mercado y Viabilidad Económico-Financiera**: Demanda, supuestos, VAN/TIR y sensibilidad
7. **Impacto Ambiental y Social**: Impactos, permisos y medidas de mitigación
8. **Plan de Implementación y Monitoreo**: Cronograma, roles, presupuesto por fase e indicadores
9. **Gestión de Riesgos y DOFA (validado)**: DOFA final, matriz de riesgos priorizada y medidas de mitigación
10. **Conclusiones y Recomendaciones**

## 🚀 Compilación del Documento

### Requisitos

Para compilar este documento necesitas una distribución de LaTeX instalada:

- **Windows**: [MiKTeX](https://miktex.org/) o [TeX Live](https://www.tug.org/texlive/)
- **macOS**: [MacTeX](https://www.tug.org/mactex/)
- **Linux**: TeX Live (disponible en repositorios)

### Compilación Local

#### Opción 1: Línea de comandos

```bash
# Compilar el documento principal
pdflatex main.tex

# Compilar bibliografía
bibtex main

# Compilar dos veces más para referencias cruzadas
pdflatex main.tex
pdflatex main.tex
```

#### Opción 2: Usando latexmk (recomendado)

```bash
latexmk -pdf -interaction=nonstopmode main.tex
```

#### Opción 3: Editor LaTeX

Abre `main.tex` en tu editor favorito:
- **TeXstudio**: F5 para compilar
- **Overleaf**: Sincronización automática
- **VS Code**: Con extensión LaTeX Workshop

### Limpieza de archivos auxiliares

```bash
# Windows (PowerShell)
Remove-Item *.aux, *.log, *.out, *.toc, *.lof, *.lot, *.bbl, *.blg

# Linux/macOS
rm -f *.aux *.log *.out *.toc *.lof *.lot *.bbl *.blg
```

## ✏️ Guía de Edición

### Agregar Nuevo Contenido

#### Agregar una nueva sección

1. Crea un archivo en `sections/` con nomenclatura `XX_nombre_seccion.tex`
2. Escribe el contenido usando comandos LaTeX
3. Incluye la sección en el capítulo correspondiente usando `\input{sections/XX_nombre_seccion}`

#### Agregar una figura

1. Coloca la imagen en la carpeta `figures/`
2. Inserta en el documento:

```latex
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{figures/nombre_imagen.png}
    \caption{Descripción de la figura}
    \label{fig:etiqueta}
\end{figure}
```

#### Agregar una tabla

```latex
\begin{table}[H]
\centering
\begin{tabular}{@{}lcc@{}}
\toprule
\textbf{Columna 1} & \textbf{Columna 2} & \textbf{Columna 3} \\ \midrule
Dato 1 & Dato 2 & Dato 3 \\
Dato 4 & Dato 5 & Dato 6 \\ \bottomrule
\end{tabular}
\caption{Descripción de la tabla}
\label{tab:etiqueta}
\end{table}
```

#### Agregar referencia bibliográfica

1. Agrega la entrada en `references/bibliography.bib`
2. Cita en el texto usando `\cite{clave_referencia}`

### Comandos Personalizados

El proyecto incluye comandos personalizados en `config/commands.tex`:

- `\nombreproyecto`: Nombre completo del proyecto
- `\piezo`: Término "piezoelectricidad" en cursiva
- `\importante{texto}`: Resalta texto importante
- `\moneda{1000}`: Formato de moneda
- `\porciento{15}`: Formato de porcentaje

## 📦 Paquetes Principales Utilizados

- **babel**: Soporte para español
- **graphicx**: Inclusión de imágenes
- **amsmath, amssymb**: Matemáticas avanzadas
- **booktabs**: Tablas profesionales
- **hyperref**: Hipervínculos y referencias
- **siunitx**: Formato de unidades
- **tikz, pgfplots**: Gráficos vectoriales
- **fancyhdr**: Encabezados personalizados

## 🎨 Personalización

### Colores del Proyecto

Los colores se definen en `config/packages.tex`:

```latex
\definecolor{azulmetro}{RGB}{0,51,102}
\definecolor{verdeenergia}{RGB}{46,125,50}
\definecolor{grisoscuro}{RGB}{66,66,66}
```

### Modificar Formato

Edita `config/format.tex` para cambiar:
- Estilo de capítulos y secciones
- Formato de captions
- Espaciado de párrafos
- Configuración de tabla de contenidos

## 📚 Referencias y Recursos

### Documentación LaTeX

- [Overleaf Documentation](https://www.overleaf.com/learn)
- [LaTeX Wikibook](https://en.wikibooks.org/wiki/LaTeX)
- [CTAN (Comprehensive TeX Archive Network)](https://www.ctan.org/)

### Sobre Piezoelectricidad

- IEEE Standard on Piezoelectricity (ANSI/IEEE Std 176-1987)
- Energy Harvesting Technologies (Priya & Inman, 2009)

## 🤝 Contribuciones

Para contribuir al documento:

1. Crea una rama para tus cambios
2. Edita los archivos necesarios
3. Compila y verifica que no haya errores
4. Haz commit con mensajes descriptivos
5. Crea un pull request

**Nota**: Los valores marcados como `[Por determinar]` o `[Por calcular]` deben ser completados durante el desarrollo del proyecto con datos reales y análisis específicos.
