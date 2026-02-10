# 📊 Análisis Exploratorio de Datos (EDA)
## Víctimas de Esterilizaciones Forzadas en Perú

[![Python](https://img.shields.io/badge/Python-3.14-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![UV](https://img.shields.io/badge/UV-Package%20Manager-green.svg)](https://docs.astral.sh/uv/)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MaryoriCruz/eda-esterilizaciones-peru/blob/main/eda_mimp.ipynb)
---

## 📋 Descripción del Proyecto

Este proyecto presenta un **Análisis Exploratorio de Datos (EDA)** sobre los casos de víctimas de esterilizaciones forzadas registrados por el Ministerio de la Mujer y Poblaciones Vulnerables (MIMP) del Perú.

El análisis transforma datos sin procesar en información clara, comprensible y útil para la toma de decisiones, lo que permitirá elaborar un informe ejecutivo fundamentado en datos verificables.

### 🎯 Objetivos del Análisis

- Comprender la estructura y calidad del dataset
- Identificar patrones temporales, geográficos y demográficos
- Evaluar limitaciones y sesgos en los datos
- Generar visualizaciones informativas y profesionales
- Proporcionar conclusiones fundamentadas para políticas públicas

---

## 🗂️ Estructura del Proyecto
```
eda-esterilizacion/
│
├── data/                           # Datos del proyecto
│   └── mimp_esterilizaciones.csv   # Dataset original
├── reports/
informe_ejecutivo.pdf
|
├── visualizations/                 # Gráficos generados durante el análisis
│   ├── 01_calidad_datos.png
│   ├── 02_evolucion_temporal.png
│   ├── 03_distribucion_geografica.png
│   ├── 04_distribucion_sexo.png
│   ├── 05_distribucion_edad.png
│   └── 06_heatmap_dept_anio.png
│
├── .venv/                          # Entorno virtual (no se sube a Git)
├── eda_mimp.ipynb                  # Notebook principal con análisis completo
├── main.py                         # Script principal (si aplica)
├── pyproject.toml                  # Configuración de dependencias (UV)
├── uv.lock                         # Lock file de UV
├── .python-version                 # Versión de Python del proyecto
├── .gitignore                      # Archivos ignorados por Git
└── README.md                       # Este archivo
```

---

## 📊 Dataset

### Fuente de Datos

- **Organización:** Ministerio de la Mujer y Poblaciones Vulnerables (MIMP)
- **Plataforma:** Datos Abiertos Perú
- **URL:** [https://www.datosabiertos.gob.pe/](https://www.datosabiertos.gob.pe/)
- **Formato:** CSV (delimitado por punto y coma)

### Contenido del Dataset

El dataset incluye información sobre:

- **Temporal:** Año de reporte de los casos
- **Geográfica:** Departamento, provincia, distrito
- **Demográfica:** Distribución por sexo y rangos de edad
- **Administrativa:** Códigos de centros, programas y servicios

### ⚠️ Advertencia sobre Calidad de Datos

**Limitación crítica detectada:** El dataset presenta ausencia total de datos en el rango etario de 18-29 años, lo cual compromete el análisis por edad. Ver sección de conclusiones en el notebook para detalles completos.

---

## 🛠️ Tecnologías Utilizadas

### Lenguaje y Entorno

- **Python:** 3.14
- **Gestor de paquetes:** UV
- **IDE:** Visual Studio Code
- **Notebook:** Jupyter

### Librerías Principales

| Librería | Versión | Propósito |
|----------|---------|-----------|
| pandas | 3.0.0 | Manipulación y análisis de datos |
| numpy | 2.4.2 | Operaciones numéricas |
| matplotlib | 3.10.8 | Visualizaciones estáticas |
| seaborn | 0.13.2 | Visualizaciones estadísticas |
| plotly | 6.5.2 | Gráficos interactivos |
| jupyter | 1.1.1 | Entorno de notebooks |

---

## 🚀 Instalación y Uso

### Prerrequisitos

- Python 3.14 instalado
- UV instalado ([Guía de instalación](https://docs.astral.sh/uv/getting-started/installation/))

### Paso 1: Clonar el repositorio
```bash
git clone https://github.com/tu-usuario/eda-esterilizacion.git
cd eda-esterilizacion
```

### Paso 2: Sincronizar dependencias con UV
```bash
# UV sincronizará automáticamente todas las dependencias del pyproject.toml
uv sync
```

### Paso 3: Activar el entorno virtual
```bash
# En Windows PowerShell
.venv\Scripts\activate

# En Linux/Mac
source .venv/bin/activate
```

### Paso 4: Ejecutar Jupyter Notebook
```bash
# Opción 1: Desde la línea de comandos
uv run jupyter notebook

# Opción 2: Abrir VS Code
code .
```

Luego abre el archivo `eda_mimp.ipynb` en VS Code o Jupyter.

---

## 📈 Principales Hallazgos

### 1. Distribución Temporal

- **Pico máximo:** 2016 con 3,580 casos reportados (58.7% del total)
- **Tendencia:** Disminución progresiva hasta 2020 (solo 3 casos)
- **Interpretación:** Refleja tanto incidencia como cambios institucionales en sistemas de registro

### 2. Distribución Geográfica

- **Mayor concentración:** Huancavelica, Ayacucho, Huánuco, Junín
- **Patrón:** Predominio en departamentos de la sierra central y sur
- **Contexto:** Regiones con mayor pobreza, ruralidad y población indígena

### 3. Distribución por Sexo

- **Mujeres:** 5,918 casos (96.9%)
- **Hombres:** 184 casos (3.1%)
- **Relación:** 32:1 (mujeres/hombres)
- **Conclusión:** Impacto desproporcionado en población femenina

### 4. Distribución por Edad

⚠️ **Limitación crítica:** Ausencia total de datos en rango 18-29 años

- **30-59 años:** 5,453 casos (99.6%)
- **60+ años:** 21 casos (0.4%)
- **Recomendación:** Verificar con fuente original antes de conclusiones sobre edad

---

## 📊 Visualizaciones

El proyecto genera 6 visualizaciones principales guardadas en `/visualizations/`:

1. **01_calidad_datos.png** - Mapa de calor de valores nulos y completitud
2. **02_evolucion_temporal.png** - Evolución de casos por año
3. **03_distribucion_geografica.png** - Casos por departamento
4. **04_distribucion_sexo.png** - Comparación por sexo (barras y pastel)
5. **05_distribucion_edad.png** - Distribución por rangos etarios
6. **06_heatmap_dept_anio.png** - Mapa de calor departamento × año

---

## ⚠️ Consideraciones Éticas

Este análisis trata sobre víctimas de esterilizaciones forzadas, un tema de alta sensibilidad que requiere:

- ✅ Respeto absoluto por la dignidad de las víctimas
- ✅ Uso responsable de los datos con fines académicos y de justicia
- ✅ Confidencialidad de información personal
- ✅ Contextualización ética de los hallazgos cuantitativos
- ✅ Compromiso con la verdad, memoria y reparación

---

## 🔬 Metodología

El análisis siguió las mejores prácticas de ciencia de datos:

1. **Exploración inicial** - Comprensión de estructura y variables
2. **Evaluación de calidad** - Detección de nulos, duplicados, inconsistencias
3. **Limpieza de datos** - Eliminación de columnas irrelevantes
4. **Análisis descriptivo** - Estadísticas por dimensión temporal, geográfica y demográfica
5. **Visualización** - Generación de gráficos profesionales
6. **Interpretación** - Contextualización crítica de hallazgos
7. **Conclusiones** - Síntesis de resultados y recomendaciones

---

## 📝 Documentación Adicional

- **Notebook completo:** `eda_mimp.ipynb` - Análisis detallado con código, visualizaciones e interpretaciones
- **Dataset:** `data/mimp_esterilizaciones.csv` - Datos originales del MIMP
- **Configuración:** `pyproject.toml` - Dependencias y configuración del proyecto

---

## 🤝 Contribuciones

Este es un proyecto académico. Si deseas contribuir:

1. Fork el repositorio
2. Crea una rama: `git checkout -b feature/nueva-funcionalidad`
3. Commit tus cambios: `git commit -m 'Añade nueva funcionalidad'`
4. Push a la rama: `git push origin feature/nueva-funcionalidad`
5. Abre un Pull Request

---

## 📚 Referencias

- [Datos Abiertos Perú - MIMP](https://www.datosabiertos.gob.pe/)
- [Defensoría del Pueblo - Informes sobre Anticoncepción Quirúrgica](https://www.defensoria.gob.pe/)
- [UV - Modern Python Package Manager](https://docs.astral.sh/uv/)

---

## 👤 Autora

**Maryori Cruz**  
Proyecto de Análisis Exploratorio de Datos  
Bootcamp de Inteligencia Artificial  
Febrero 2026

---

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo `LICENSE` para más detalles.

---

## 🙏 Agradecimientos

- Ministerio de la Mujer y Poblaciones Vulnerables (MIMP) por datos abiertos
- Plataforma Datos Abiertos Perú
- Comunidad de Python y ciencia de datos
- Víctimas y organizaciones que luchan por justicia y reparación

---

**⭐ Si este proyecto te resultó útil, considera darle una estrella en GitHub**

---

*Este análisis se realizó con fines académicos y de investigación, con el máximo respeto por las víctimas de esterilizaciones forzadas en el Perú.*