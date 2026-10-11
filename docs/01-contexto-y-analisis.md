# 1. Contexto y análisis de WannaLocker

## 1.1 Resumen ejecutivo

WannaLocker se ha descrito en investigaciones públicas como ransomware dirigido a dispositivos Android. El ransomware es una categoría de malware que restringe el acceso a información o al dispositivo y puede exigir un pago para intentar recuperarlo. El nombre WannaLocker recuerda a WannaCry, pero no debe asumirse que sean la misma familia o que compartan la misma plataforma objetivo.

La información técnica sobre una familia de malware puede variar entre muestras, campañas y versiones. Por ello, este documento distingue entre el contexto general de ransomware móvil y los hechos que deben verificarse en una muestra concreta.

## 1.2 Objetivo del análisis

- Entender el impacto potencial para la confidencialidad, integridad y disponibilidad de datos.
- Identificar señales que justifiquen una investigación.
- Definir un procedimiento de análisis seguro y reproducible.
- Recomendar controles de prevención y respuesta.

## 1.3 Riesgos generales del ecosistema Android

Los escenarios de riesgo comunes incluyen aplicaciones instaladas desde fuentes no confiables, suplantación de aplicaciones legítimas, permisos que no concuerdan con la función anunciada, sistemas desactualizados y copias de seguridad inexistentes o no verificadas. Estos factores son riesgos generales y no prueban por sí solos que una muestra sea WannaLocker.

Android usa un modelo de permisos y aislamiento entre aplicaciones. Los permisos concedidos pueden permitir acceso a datos o acciones restringidas; por eso deben evaluarse según la función legítima de la aplicación. Véanse las referencias oficiales en [Fuentes y limitaciones](05-fuentes-y-limitaciones.md).

## 1.4 Impacto potencial

| Dimensión | Impacto posible | Evidencia que conviene registrar |
|---|---|---|
| Disponibilidad | Archivos o funciones dejan de estar accesibles | Síntomas, hora de inicio, mensajes mostrados |
| Integridad | Archivos modificados o renombrados inesperadamente | Inventario de archivos, hashes y cambios observados |
| Confidencialidad | Riesgo adicional si el malware también recopila datos | Indicadores corroborados; no inferir exfiltración sin evidencia |
| Operación | Pérdida de productividad o necesidad de restaurar el dispositivo | Tiempo de interrupción y acciones de recuperación |

## 1.5 Modelo de análisis

1. **Identificación:** registrar el origen del archivo, tamaño, nombre y SHA-256.
2. **Inspección estática:** revisar el contenedor APK, manifiesto, permisos, recursos y cadenas relevantes sin ejecutar la aplicación.
3. **Correlación:** comparar hallazgos con fuentes técnicas confiables y, cuando sea apropiado, con indicadores conocidos.
4. **Análisis dinámico controlado:** solo por personal capacitado, en un laboratorio aislado, con una muestra autorizada y procedimientos de contención documentados.
5. **Conclusión:** etiquetar el resultado como no concluyente, requiere revisión o confirmado con evidencia suficiente; explicar el fundamento.

## 1.6 Principios de calidad

- No confundir coincidencias de texto con prueba de malware.
- No asumir que un permiso es malicioso sin analizar el contexto.
- Separar observaciones, hipótesis e inferencias.
- Registrar las versiones de las herramientas y la fecha del análisis.
- No ejecutar una muestra sospechosa en un dispositivo personal.
