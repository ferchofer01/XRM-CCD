# XRM-CCD

Aplicación de consulta y reporte de vulnerabilidades.

## Requisitos

- Python 3.9 o superior.
- Acceso a Internet para consumir las API de NVD y OSV.
- (Opcional) Definir la variable de entorno `NVD_API_KEY` si se dispone de una clave para la API de NVD a fin de evitar límites o bloqueos.

## Ejecución

```bash
python app/vulnerability_consultant.py
```

## Funcionalidades

- Buscar vulnerabilidades por nombre o palabra clave directamente en la API pública de NVD.
- Consultar una vulnerabilidad específica por su identificador (por ejemplo, CVE-2023-12345) utilizando las API de OSV y NVD.
- Mostrar la descripción, severidad, enlaces oficiales y pasos sugeridos de remediación de cada vulnerabilidad recuperada.
- Agregar vulnerabilidades seleccionadas a un reporte y generar un archivo Markdown con la información recopilada.

Los reportes se guardan en la carpeta `reports/` dentro del proyecto.
