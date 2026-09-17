# 📄 Contract Automation System — Generador Masivo de Contratos con Django
> **Plataforma web empresarial para la generación masiva y automatizada de contratos legales y comerciales, combinando plantillas Word (.docx) con bases de datos Excel.**

[![Framework](https://img.shields.io/badge/Backend-Django%205.x%20%7C%20Python%203.13-092e20.svg)](#-stack-tecnológico)
[![Document Engine](https://img.shields.io/badge/Docx-python--docx%20%7C%20OpenPyXL-blue.svg)](#-características-del-sistema)
[![Status](https://img.shields.io/badge/Status-Active%20Development-success.svg)](#)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---

## 📌 El Desafío de Negocio

En despachos legales, empresas inmobiliarias, departamentos de Recursos Humanos y agencias de servicios, la redacción de contratos es un cuello de botella constante:

- **Lentitud Operativa**: Redactar individualmente decenas o cientos de contratos cambiando manualmente nombres, DNIs, direcciones, sueldos o cláusulas específicas demora días completos de trabajo.
- **Riesgo Legal por Errores Humanos**: Una letra cambiada en un apellido, un dígito erróneo en el salario o una fecha incorrecta pueden anular la validez legal de un contrato o provocar litigios costosos.
- **Falta de Estandarización**: Dificultad para mantener actualizadas las versiones oficiales de las plantillas entre los miembros del equipo.

---

## 💡 La Solución Implementada

**Contract Automation System** es una aplicación web robusta desarrollada con el framework **Django** que centraliza, automatiza y asegura todo el ciclo de generación documental:

1. **Gestión Inteligente de Plantillas Word (`PlantillaContrato`)**:
   - Los usuarios suben sus formatos en `.docx`.
   - El sistema analiza el documento y **extrae automáticamente todos los marcadores o placeholders** dinámicos (ej: `{{NOMBRE_COMPLETO}}`, `{{DNI}}`, `{{SALARIO}}`), almacenándolos de manera estructurada en campos `JSONField`.
2. **Carga y Validación de Fuentes de Datos (`FuenteDeDatos`)**:
   - Soporte para archivos Excel (`.xlsx`).
   - Mapeo automático de las columnas del archivo para vincularlas de forma visual e intuitiva con los placeholders de las plantillas.
3. **Generación por Lotes en Segundos**:
   - Combina la plantilla con cada fila del Excel, generando contratos individuales listos para descargar, imprimir o enviar a firma digital.

---

## 📈 Impacto y Mejoras Conseguidas

| Proceso | Método Tradicional (Manual) | Con Contract Automation System | Mejora Conseguida |
|---|---|---|---|
| **Tiempo de Generación (100 contratos)** | ~15 a 20 horas de tipeo y revisión | Menos de 15 segundos | **Reducción del 98% en tiempo operativo** |
| **Margen de Error Tipográfico** | Alta probabilidad (errores humanos en copiado/pegado) | Cero errores (mapeo directo desde la base de datos validada) | **Seguridad jurídica y precisión absoluta** |
| **Control de Versiones** | Archivos dispersos en carpetas locales | Plantillas centralizadas por usuario con control de acceso | **Estandarización corporativa de documentos** |
| **Autonomía del Usuario** | Dependencia de programadores para cambiar plantillas | Cualquier usuario sube su Word y el sistema detecta variables | **Adopción inmediata sin conocimientos técnicos** |

---

## ✨ Características Técnicas del Sistema

- **Arquitectura MVT de Django**: Código limpio, modular, desacoplado y preparado para escalar.
- **Extracción Dinámica de Placeholders**: Algoritmo para parsear párrafos y tablas en archivos Word sin corromper el formato ni el diseño visual original.
- **Modelos de Datos Flexibles con JSONField**: Almacenamiento ágil de metadatos de plantillas y esquemas de columnas en base de datos sin requerir migraciones complejas por cada nuevo tipo de documento.
- **Gestión Multi-Usuario y Seguridad**: Modelo de propiedad de plantillas y fuentes de datos vinculado a `AUTH_USER_MODEL` con políticas de eliminación en cascada.
- **Vistas Web Intuitivas**: Interfaces de usuario dedicadas para:
  - `gestion_plantillas.html`: Subida, previsualización y listado de formatos de contrato.
  - `gestion_fuentes_datos.html`: Carga, validación de columnas y administración de archivos Excel.

---

## 🛠️ Stack Tecnológico

- **Backend**: Python 3.13, Django Framework 5.x.
- **Procesamiento Documental**: `python-docx`, `openpyxl`, `pandas`.
- **Persistencia**: SQLite (desarrollo) / PostgreSQL (listo para producción).
- **Frontend**: HTML5, CSS3, plantillas Django (Django Template Language).

---

## 🗂️ Estructura del Proyecto

```text
├── contract_automation_system/
│   ├── contract_generator/        # Configuración principal de Django (settings, urls, wsgi/asgi)
│   ├── generator/                 # Aplicación central de generación
│   │   ├── models.py              # Modelos PlantillaContrato y FuenteDeDatos con JSONField
│   │   ├── views.py               # Lógica de carga, extracción y combinación de datos
│   │   ├── urls.py                # Rutas de la aplicación
│   │   └── templates/generator/   # Vistas de gestión de plantillas y fuentes de datos
│   ├── manage.py                  # CLI de administración de Django
│   ├── requirements.txt           # Dependencias del proyecto
│   └── README.md                  # Documentación del proyecto
```

---

## 🚀 Instalación y Puesta en Marcha

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/Enybyy/contract-automation-system.git
   cd contract-automation-system
   ```

2. **Crear y activar un entorno virtual:**
   ```bash
   python -m venv venv
   # En Windows:
   .\venv\Scripts\activate
   # En Linux/macOS:
   source venv/bin/activate
   ```

3. **Instalar dependencias:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Ejecutar migraciones de base de datos:**
   ```bash
   python manage.py migrate
   ```

5. **Iniciar el servidor de desarrollo:**
   ```bash
   python manage.py runserver
   ```
   Accede en tu navegador a: `http://127.0.0.1:8000/`

---

## 📬 ¿Quieres automatizar la documentación de tu empresa?

Desarrollo **plataformas web personalizadas en Django, sistemas SaaS para automatización de documentos y portales internos a medida**.

- **GitHub**: [@Enybyy](https://github.com/Enybyy)
- **Perfil Profesional**: Eliud RM — Data Science & Software Solutions
- *Escríbeme para evaluar cómo automatizar los procesos documentales de tu negocio.*
