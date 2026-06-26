# Reporte de Análisis de Seguridad: scanme.nmap.org

## 📋 Resumen Ejecutivo
Este análisis se realizó con el objetivo de evaluar la superficie de ataque del host `scanme.nmap.org`. Se identificaron los servicios expuestos y las versiones de software en ejecución para determinar posibles vectores de riesgo, siguiendo una metodología de escaneo estándar.

## 🌐 Alcance (Scope)
* **Objetivo:** `scanme.nmap.org` (45.33.32.156)
* **Fecha de análisis:** 26 de junio de 2026

## 🛠️ Metodología
Se utilizaron las siguientes herramientas para la enumeración de red:
1. `ss -tuln`: Listado de puertos en escucha local.
2. `nmap`: Escaneo de puertos remotos para identificación de servicios.
3. `nmap -sV`: Detección de versiones de servicios.

## 🔍 Hallazgos
| Puerto/Servicio | Versión | Notas |
| :--- | :--- | :--- |
| 22/tcp (SSH) | OpenSSH 6.6.1p1 | Gestión remota |
| 80/tcp (HTTP) | Apache 2.4.7 | Servidor web |
| 9929/tcp | Nping echo | Ecos de red |
| 31337/tcp | Elite | tcprewrapped |

## 🛡️ Recomendaciones
* **Seguridad SSH:** El puerto 22 está expuesto a internet, lo cual facilita ataques de fuerza bruta. Se recomienda implementar autenticación basada en claves (SSH keys) y deshabilitar el acceso mediante contraseña para proteger la confidencialidad e integridad del sistema.
* **Mantenimiento:** Apache 2.4.7 es una versión antigua. Se recomienda verificar parches de seguridad o actualizar a una versión estable soportada para mitigar posibles vulnerabilidades conocidas.
