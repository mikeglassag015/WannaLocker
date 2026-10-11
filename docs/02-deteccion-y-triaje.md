# 2. Detección y triaje defensivo

## 2.1 Señales que requieren revisión

- Aparece una nota de rescate o una exigencia de pago inesperada.
- Archivos personales dejan de abrirse o cambian de nombre de forma repentina.
- Se instaló recientemente una aplicación desde una fuente desconocida.
- Una aplicación solicita permisos que parecen no guardar relación con su función.
- Google Play Protect o una solución de seguridad muestra una alerta.
- El comportamiento del dispositivo cambia abruptamente tras instalar una aplicación.

Ninguna señal aislada confirma WannaLocker. Los fallos de almacenamiento, las aplicaciones defectuosas y otros tipos de malware pueden producir síntomas similares.

## 2.2 Triaje inicial

1. Anotar la fecha, hora, zona horaria y síntomas observados.
2. No abrir de nuevo la aplicación sospechosa ni intentar reinstalarla.
3. Si se sospecha actividad maliciosa en curso, desconectar temporalmente el dispositivo de redes cuando sea compatible con las necesidades de preservación de evidencia.
4. Evitar borrar archivos, restablecer el teléfono o instalar herramientas al azar antes de decidir si es necesario preservar evidencia.
5. Desde un equipo confiable, revisar cuentas importantes y sesiones activas si existe posibilidad de exposición de credenciales.
6. Escalar el caso al equipo de TI, fabricante o especialista de respuesta a incidentes.

## 2.3 Análisis estático de APK

El análisis estático examina el archivo como datos, sin instalarlo ni ejecutarlo. Un flujo básico es:

- Calcular SHA-256 y registrar el tamaño del archivo.
- Confirmar que el archivo tiene una estructura APK/ZIP válida.
- Examinar el manifiesto y los permisos declarados.
- Revisar metadatos, nombres de componentes y cadenas relevantes.
- Comparar el hash con fuentes reputables, si existe una coincidencia verificable.
- Documentar falsos positivos, límites del método y resultados no concluyentes.

Las aplicaciones pueden estar ofuscadas, empaquetadas o contener recursos cifrados. Una inspección estática sencilla puede no identificar comportamientos ocultos.

## 2.4 Uso de ADB

ADB puede utilizarse para consultas de diagnóstico en un dispositivo propio o autorizado. Antes de recopilar información:

- Explica al propietario qué datos se recogerán.
- Activa la depuración USB solo cuando sea necesaria.
- Autoriza únicamente el equipo de análisis esperado.
- No compartas números de serie, inventarios de aplicaciones ni registros sin sanitizarlos.
- Desactiva la depuración USB al terminar.

## 2.5 Niveles de confianza sugeridos

| Nivel | Significado | Acción |
|---|---|---|
| Informativo | Observación aislada sin corroboración | Registrar y observar |
| Revisión necesaria | Varios indicios o comportamiento anómalo | Análisis técnico autorizado |
| Alta sospecha | Evidencia consistente de actividad dañina | Aislar, preservar evidencia y escalar |
| Confirmado | Evidencia técnica suficiente, validada por analista | Activar el plan formal de respuesta |

Estos niveles son una guía documental, no una clasificación automática.
