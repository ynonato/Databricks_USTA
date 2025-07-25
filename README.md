# 🚛 Ingesta Masiva de Datos Públicos – SECOP Colombia

Este proyecto documenta el proceso de **ingeniería de datos** enfocado en la **ingesta masiva, limpieza y almacenamiento local** de datos del sistema de contratación pública colombiano (SECOP).

## 🎯 Objetivo

Desarrollar un pipeline reproducible y escalable para la recolección de datos desde fuentes públicas (API del SECOP), que permita su posterior análisis y visualización.

## 🛠️ Descripción Técnica

- **Origen de datos**: API oficial de datos abiertos del SECOP.
- **Carga masiva**: los datos se descargan en bloques de 500.000 registros para evitar saturación de memoria.
- **Identificación única**: se crea un hash (SHA-256) a partir de columnas clave para asegurar la unicidad de los registros.
- **Almacenamiento**: los datos procesados se guardan localmente en una base de datos SQLite.

## ⚙️ Stack Tecnológico

- `Python` (pandas, requests, hashlib, sqlite3)
- `SQLite` para almacenamiento relacional
- `Google Colab` como entorno de desarrollo activo
- `Google Drive` para respaldo y persistencia
- **Inicialmente desarrollado como un job en Databricks (PySpark)** y luego migrado a Colab debido a limitaciones de la versión gratuita.

## 🧱 Ingeniería de Datos

- Control de errores en la ingesta por lotes.
- Concatenación y validación de integridad.
- Consolidación de un único archivo .db.


## 🚧 Consideraciones

Debido a las restricciones de la versión gratuita de Databricks (tiempo de sesión, recursos), se migró la lógica de ingestión a Google Colab, donde es posible continuar el desarrollo de forma gratuita y con almacenamiento persistente.

## 📌 Próximos pasos

- Modularizar funciones de ingesta y limpieza.
- Automatizar la actualización periódica de datos.
- Conectar con herramientas de visualización o dashboards interactivos.


