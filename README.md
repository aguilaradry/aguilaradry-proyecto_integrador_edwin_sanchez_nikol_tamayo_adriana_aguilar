## Proyecto de Ingesta de Datos desde una API a SQLite

## aguilaradry-proyecto_integrador_edwin_sanchez_nikol_tamayo_adriana_aguilar

### Descripción del Proyecto  

Este proyecto automatiza la extracción, almacenamiento y validación de datos desde la API [Sample APIs - Nintendo Switch Games](https://api.sampleapis.com/switch/games) hacia una base de datos SQLite, generando además archivos de auditoría y evidencia en Excel. Todo el desarrollo se realizó en **GitHub Codespaces**.

La automatización se realiza mediante **GitHub Actions**, garantizando que los datos se actualicen sin intervención manual.  


### Metodología de Desarrollo  

#### **Extracción de Datos desde el API**  
- Se seleccionó la API de videojuegos de Nintendo Switch.
- Se creó un script en Python para consumir la API usando `requests`.  
- Se procesaron los datos extraídos asegurando su correcta estructura. 

#### **Almacenamiento en Base de Datos SQLite**  
- Se creó una base de datos en `src/bigdata/static/db/ingestion.db`.
- Se diseñó un esquema con una tabla `videojuegos` para almacenar los datos.
- Se insertaron los datos extraídos de la API en la base de datos.

#### **Generación de Evidencias**  
- **Archivo Excel**: Se usa `pandas` para exportar los datos a `ingestion.xlsx`.  
- **Archivo de Auditoría**: Se compara la cantidad de registros obtenidos de la API y los almacenados en la base de datos. 

#### **Automatización con GitHub Actions**  
- Se configuró un **workflow** que ejecuta la extracción, almacenamiento y generación de evidencias automáticamente.  
- Se verifica que la base de datos y los archivos generados sean correctos.  


### 📂 Estructura del Proyecto  

[proyecto_integrador_edwin_sanchez_nikol_tamayo_adriana_aguilar]
├── setup.py
├── README.md
├── .github
│   └── workflows
│       └── test_actividad1.yml
└── src
    ├── static
    │   ├── auditoria
    │   │   └── ingestion.txt
    │   ├── db
    │   │   └── ingestion.db
    │   └── xlsx
    │       └── ingestion.xlsx
    └── ingestion.py

### **Automatización con GitHub Actions**
El proyecto usa GitHub Actions para ejecutar la ingesta de datos automáticamente.
Srchivo: .github/workflows/test_actividad1.yml
- Se crea un entorno virtual (python -m venv venv)
- Se activa el entorno virtual (./venv/Scripts/activate )
- Se actualiza pip (pip install --upgrade pip)
- Instalación de dependencias (pip install -e .)
- Ejecución del script (python src/bigdata/ingestion.py)
- Commit y push de los cambios

### **Tecnologías Utilizadas**
- Python (Requests, SQLite3, Pandas, OpenPyXL)
- GitHub Codespaces (para desarrollo en la nube)
- GitHub Actions (para la automatización del proceso)
- SQLite (como base de datos para almacenamiento)

Este proyecto permite la extracción y almacenamiento de datos de videojuegos de Nintendo Switch de manera estructurada y automatizada. Gracias a Codespaces, todo el desarrollo se realizó en la nube sin necesidad de configuraciones locales. Además, la integración con GitHub Actions garantiza la ejecución automática y reproducible del proceso.
