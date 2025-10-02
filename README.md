# XRM-CCD

Aplicación de consulta y reporte de vulnerabilidades.

## Requisitos

- Python 3.9 o superior.
- Acceso a Internet para consultar las APIs públicas de NVD, OSV y el portal de plugins de Tenable.
- (Opcional) Definir la variable de entorno `NVD_API_KEY` si se dispone de una clave para la API de NVD a fin de evitar límites o bloqueos.
- Definir las variables de entorno `TENABLE_ACCESS_KEY` y `TENABLE_SECRET_KEY` con las credenciales de Tenable.io necesarias para consultar la biblioteca oficial de plugins.

## Ejecución

```bash
python app/vulnerability_consultant.py
```

### Configuración de credenciales

Antes de ejecutar la aplicación asegúrate de definir las credenciales necesarias como variables de entorno:

```bash
export TENABLE_ACCESS_KEY="<tu_access_key>"
export TENABLE_SECRET_KEY="<tu_secret_key>"
# Opcional para evitar límites en la API de NVD
export NVD_API_KEY="<tu_api_key>"
```

La herramienta validará la presencia de las credenciales de Tenable antes de intentar realizar búsquedas en esa fuente.

## Funcionalidades

- Buscar vulnerabilidades por nombre o palabra clave combinando resultados de la API pública de NVD y de los plugins oficiales de Tenable (https://www.tenable.com/plugins/nessus/).
- Consultar una vulnerabilidad específica por su identificador (por ejemplo, CVE-2023-12345 o el ID numérico de un plugin de Tenable) utilizando las API de OSV, NVD y Tenable.
- Mostrar la descripción, severidad, enlaces oficiales y pasos sugeridos de remediación de cada vulnerabilidad recuperada.
- Agregar vulnerabilidades seleccionadas a un reporte y generar un archivo Markdown con la información recopilada.

Los reportes se guardan en la carpeta `reports/` dentro del proyecto.
