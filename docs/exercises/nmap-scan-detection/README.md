## Ejercicio sobre deteccón de scaneo Nmap en Wireshark

En este ejercicio vamos a realizar el análisis de un equipo Ubuntu mediante el uso de la herramienta Nmap desde un 
equipo Kali.

## Objetivo

Comprobar que tipo de información podemos llegar a obtener de un equipo Ubuntu al cual le hemos activado de manera
previa el firewall UFW.

## Metodología de ataque y defensa

Se ha realizado un escaneo agresivo mediante el comando nmap -A 10.0.2.15

Dicho escaneo se ha detectado gracias al uso de la herramienta Wireshark mediante la cual hemos podido obtener
el aviso de detección de dicho escaneo, contando con información como la dirección ip del atacante y el tipo
de escaneo realizado.

## Resultado del escaneo

Host: 10.0.2.15 (Ubuntu)
Estado: Up (0.00077s latency)
Puertos escaneados: 1000 puertos comunes
Puertos encontrados: 22/tcp closed (ssh) | 999 puertos: filtered (no response)
Detección de OS: Linux 2.6.X (resultado poco fiable)
MAC Address: 08:00:27:29:5E:79 (Oracle VirtualBox)

## Hallazgos de Seguridad

Firewall Efectivo: 999 aparecen como "filtered"
SSH Seguro: Puerto 22 cerrado (no expuesto)
Detección Exitosa: Patrón de escaneo claramente visible en Wireshark

## Archivos Incluidos
nmap_scan_results.txt: salida completa del escaneo
nmap_scan_capture.pcap: captura de tráfico del escaneo
analysis.md: análisis técnico detallado

## Conclusión

El firewall UFW demostró ser efectivo bloqueando la mayoría de puertos, mientras que Wireshark permitio detectar
inmediatamente la actividad de reconocimiento.
