**RETO 1: INVESTIGACIÓN DE SYSLOG**

**Concepto**: Los niveles de Syslog son valores numéricos que determinan la gravedad de un evento. Incluye ocho niveles distintos que van del 0 al 7 y se clasifican desde el nivel de gravedad más alto al más bajo.

| valor | gravedad | descripción |
| :---- | :---- | :---- |
| 0 | emergencia | el sistema es inutilizable |
| 1 | alerta | deben tomarse medidas de inmediato |
| 2 | crítico | condiciones críticas |
| 3 | error | condiciones de error |
| 4 | advertencia | condiciones de advertencia |
| 5 | aviso | afección normal pero significativa |
| 6 | informativo | mensajes informativos |
| 7 | depurar | mensajes de nivel de depuración |

1. ¿Por qué es una negligencia grave que el archivo */var/log/auth.log* tenga permisos de lectura para usuarios no privilegiados?

Que el archivo */var/log/auth.log* tenga permisos de lectura para usuarios no privilegiados  se considera una **vulnerabilidad crítica** porque expone información crítica sobre la  autenticación y la estructura del sistema, facilitando la escalada de privilegios y ataques dirigidos.

2. ¿Qué información específica (como PIDs, nombres de usuario o direcciones IP) diferencia un intento fallido de conexión remota *SSH* de un simple fallo de contraseña de un usuario local frente a la pantalla?

**Fallo de conexión remota SSH:** Los fallos de conexiones SSH surgen porque en lugar de que el servidor esté en ejecución para poder aceptar conexiones, el servicio está inactivo o ha fallado, por lo tanto se rechazará todos los intentos de conexión. Para solucionar el problema, debemos comprobar el estado del servicio SSH y reiniciarlo si es necesario.

**Fallo de conexión de un usuario local**: Puede ocurrir por diferencias entre las versiones de Windows, la configuración en la red y si las actualizaciones recientes de seguridad están afectando cómo SMB verifica tu identidad.

**RETO 2: DIALNET (LOG MANAGEMENT).**  
A nivel empresarial y legal . mover los registros a un servidor externo seguro no es solo una buena práctica, sino una necesidad estratégica por diferentes razones:

- Si un atacante logra acceso de superusuario (root) en un servidor su primera acción suele ser borra o modificar /var/log/auth.log para ocultar su rastro.  
- Al enviar logs en tiempo real a un servidor externo, el rastro digital se vuelve indeleble, permitiendo a los administradores reconstruir el incidente incluso si la máquina original queda inoperativa.  
- Permite detectar ataques distribuidos que afectan a múltiples máquinas simultáneamente, algo imposible si los registros están dispersos e inconexos.

\[1\] ManageEngine, “Syslog Levels: Detailed Guide on Syslog Severity Levels,” *manageengine.com*. \[En línea\]. Disponible en: [https://www.manageengine.com/products/eventlog/logging-guide/syslog/syslog-levels.html](https://www.manageengine.com/products/eventlog/logging-guide/syslog/syslog-levels.html).

\[2\] Hardware Premium, “Linux: Acceso de usuarios y fallo de certificados,” *hardwarepremium.com*. \[En línea\]. Disponible en: [https://www.hardwarepremium.com/noticias/40214/linux-acceso-usuarios-fallo-certificados/](https://www.hardwarepremium.com/noticias/40214/linux-acceso-usuarios-fallo-certificados/).

\[3\] Microsoft Learn, “Fallo de conexión en red local,” *learn.microsoft.com*. \[En línea\]. Disponible en: [https://learn.microsoft.com/en-us/answers/questions/5625286/fallo-de-conexion-en-red-local](https://learn.microsoft.com/en-us/answers/questions/5625286/fallo-de-conexion-en-red-local).
