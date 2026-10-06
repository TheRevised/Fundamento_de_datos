# Análisis y procesamiento de datos de voz

Proyecto académico de la materia **Análisis y Procesamiento de Datos**. El repositorio contiene un conjunto de grabaciones de voz y sus características acústicas calculadas para servir como base de exploración y análisis de datos.

> **Estado actual:** los datos y el entorno de dependencias están incluidos. El archivo `main.ipynb` se conserva como cuaderno de trabajo, pero actualmente no contiene celdas de análisis.

## Objetivo

Organizar y documentar un conjunto de datos de voz para estudiar variables relacionadas con frecuencia fundamental, energía, cruces por cero y características espectrales. El archivo tabular también incluye una etiqueta de género (`H` o `M`) asociada con cada grabación.

## Estructura del proyecto

```text
.
├── data/
│   ├── hombre/              # 100 archivos de audio .wav
│   └── mujer/               # 100 archivos de audio .wav
├── main.ipynb               # Cuaderno principal de análisis
├── requirements.txt         # Dependencias de Python
├── voice_features.csv       # Características acústicas de 200 audios
├── .gitignore
└── README.md
```

## Datos disponibles

`voice_features.csv` contiene **200 registros** y las siguientes **14 columnas**:

| Columna | Descripción |
| --- | --- |
| `f0_hz` | Frecuencia fundamental |
| `f1_hz`, `f2_hz`, `f3_hz` | Primeros formantes |
| `zcr` | Tasa de cruces por cero |
| `spectral_rolloff_hz` | Rolloff espectral |
| `spectral_centroid_hz` | Centroide espectral |
| `spectral_bandwidth_hz` | Ancho de banda espectral |
| `rms_energy` | Energía RMS |
| `tempo_bpm` | Tempo estimado en pulsaciones por minuto |
| `onset_strength` | Fuerza de los ataques |
| `hnr_db` | Relación armónico-ruido en decibeles |
| `archivo` | Nombre del archivo de audio de origen |
| `genero` | Etiqueta presente en los datos: `H` o `M` |

### Resumen descriptivo inicial

| Variable | Mínimo | Máximo | Promedio |
| --- | ---: | ---: | ---: |
| `f0_hz` | 94.3793 | 211.2128 | 162.9170 |
| `zcr` | 0.0430 | 0.2184 | 0.1080 |
| `spectral_centroid_hz` | 1102.0941 | 2526.1251 | 1707.2274 |
| `rms_energy` | 0.0370 | 0.1554 | 0.0888 |
| `hnr_db` | 12.8160 | 22.7475 | 16.9671 |

Estos valores son únicamente un resumen descriptivo del CSV incluido; no representan un modelo predictivo ni permiten afirmar conclusiones estadísticas sin un análisis adicional.

## Requisitos

- Python 3.10 o superior
- Jupyter Notebook o JupyterLab
- Las dependencias listadas en `requirements.txt`

## Instalación

Desde la carpeta raíz del proyecto, crea y activa un entorno virtual:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Si Windows bloquea la ejecución de scripts de PowerShell, puede utilizarse un intérprete compatible o activar el entorno desde otra terminal. No es necesario versionar la carpeta `.venv`.

## Ejecución

1. Activa el entorno virtual.
2. Inicia Jupyter:

   ```powershell
   jupyter notebook
   ```

3. Abre `main.ipynb`.
4. Utiliza `voice_features.csv` como fuente tabular y `data/` para acceder a los audios originales.

## Consideraciones de reproducibilidad

- Las rutas deben resolverse desde la raíz del repositorio.
- El CSV utiliza los nombres de archivo de audio en la columna `archivo`.
- `tempo_bpm` contiene valores con formato de arreglo en los registros actuales; conviene normalizarlos antes de realizar cálculos numéricos.
- Las etiquetas `H` y `M` se documentan tal como aparecen en el archivo y no implican una interpretación adicional sobre la identidad de las personas grabadas.
- Antes de redistribuir públicamente los audios, verifica que su fuente y licencia permitan compartirlos.

## Próximos pasos sugeridos

- Cargar y validar el CSV con `pandas`.
- Limpiar y convertir las columnas que contienen valores no escalares.
- Explorar distribuciones y correlaciones entre características acústicas.
- Comparar las variables por etiqueta mediante visualizaciones y estadística descriptiva.
- Documentar cualquier modelo, métrica y conclusión en `main.ipynb`.

## Licencia

No se declara una licencia de distribución en este repositorio. Antes de publicarlo, confirma los permisos de uso y redistribución de los audios y añade una licencia acorde con la procedencia de los datos.
# Fundamento_de_datos
