# WannaLocker en Android: análisis, detección y prevención

> **Proyecto de investigación defensiva y documentación técnica.** No incluye muestras de malware, instrucciones para desplegarlo ni herramientas para cifrar archivos.

[![Idioma](https://img.shields.io/badge/idioma-español-blue)](#idioma)
[![Enfoque](https://img.shields.io/badge/enfoque-defensivo-green)](#alcance-y-uso-responsable)
[![Estado](https://img.shields.io/badge/estado-documentación%20académica-lightgrey)](#estado-del-proyecto)

## Descripción

Este repositorio estudia **WannaLocker**, una familia de ransomware para Android descrita en informes públicos de seguridad. El objetivo es organizar una investigación reproducible sobre el contexto de la amenaza, sus posibles indicadores, la respuesta ante incidentes y las medidas de prevención para usuarios y administradores de dispositivos Android.

WannaLocker no debe confundirse con **WannaCry**, el brote de ransomware ampliamente conocido por afectar sistemas Windows. Las características exactas pueden variar entre muestras; cualquier afirmación técnica específica debe estar respaldada por un informe verificable y la muestra correspondiente.

## Objetivos

- Explicar el riesgo que representa el ransomware móvil.
- Describir un proceso seguro de análisis estático de aplicaciones Android (APK).
- Documentar indicadores que justifiquen una revisión adicional, sin tratarlos como prueba definitiva.
- Establecer una guía de respuesta y recuperación.
- Proponer controles preventivos para usuarios, equipos de soporte y organizaciones.
- Mantener un registro transparente de fuentes, limitaciones y evidencias.

## Estructura del repositorio

```text
WannaLocker-Android-Research/
├── README.md
├── LICENSE
├── SECURITY.md
├── CONTRIBUTING.md
├── docs/
│   ├── 01-contexto-y-analisis.md
│   ├── 02-deteccion-y-triaje.md
│   ├── 03-respuesta-y-recuperacion.md
│   ├── 04-prevencion.md
│   └── 05-fuentes-y-limitaciones.md
└── reports/
    └── plantilla-informe.md
```

## Guía de lectura

1. [Contexto y análisis](docs/01-contexto-y-analisis.md)
2. [Detección y triaje](docs/02-deteccion-y-triaje.md)
3. [Respuesta y recuperación](docs/03-respuesta-y-recuperacion.md)
4. [Prevención](docs/04-prevencion.md)
5. [Fuentes y limitaciones](docs/05-fuentes-y-limitaciones.md)
6. [Plantilla de informe](reports/plantilla-informe.md)

## Metodología recomendada

1. **Definir alcance y autorización:** indicar quién autoriza el análisis, qué dispositivo o archivo se examina y con qué propósito.
2. **Preservar evidencia:** registrar fecha y hora, versión de Android, origen del archivo y hash SHA-256 cuando corresponda.
3. **Analizar sin ejecutar:** revisar metadatos, manifiesto, permisos y estructura del APK en un entorno controlado; no instalar la aplicación sospechosa en un teléfono personal.
4. **Corroborar indicadores:** contrastar los resultados con varias fuentes reputables y evitar conclusiones basadas en un único indicador.
5. **Documentar resultados:** separar hechos observados, hipótesis y conclusiones; registrar herramientas y versiones.
6. **Sanitizar antes de publicar:** eliminar identificadores de dispositivo, cuentas, nombres, tokens, datos privados y muestras no autorizadas.

## Herramientas que pueden formar parte de un análisis autorizado

- **Android Debug Bridge (ADB):** consulta información de diagnóstico en dispositivos autorizados.
- **Android Studio / SDK Platform Tools:** herramientas oficiales para desarrollo y diagnóstico Android.
- **MobSF:** plataforma de análisis de seguridad móvil; úsala en un entorno controlado y siguiendo su documentación.
- **Androguard:** biblioteca para inspeccionar aspectos estructurales de APK y DEX.
- **SHA-256:** huella criptográfica para identificar y comparar archivos.

Estas herramientas no garantizan la detección de todas las variantes. La interpretación debe realizarla una persona con conocimientos de seguridad móvil.

## Alcance y uso responsable

- Este proyecto es educativo y defensivo.
- No distribuye WannaLocker ni otras muestras maliciosas.
- No garantiza que un dispositivo esté limpio ni que un archivo sea seguro.
- Solo analiza sistemas, dispositivos y archivos propios o con autorización explícita.
- No subas archivos privados o muestras sensibles a servicios públicos sin autorización.
- No publiques informes con información personal o identificadores de dispositivos.

## Estado del proyecto

La documentación es una base de investigación. Antes de presentar conclusiones sobre una variante específica, añade referencias verificables, fechas de consulta, metodología y evidencias reproducibles. No declares una detección confirmada sin corroboración suficiente.

## Licencia

El contenido original de este repositorio se publica bajo la licencia MIT. Las marcas, herramientas y documentos externos citados pertenecen a sus respectivos titulares.
