## Resultados del escaneo Nmap

- **Comando utilizado**: `nmap -A 10.0.2.15`
- **Tiempo de escaneo**: `11.04 segundos`
- **Técnicas aplicadas**: 
	- TCP SYN Scan
	- OS Detection
	- Service Version Detection
- **Estado de los puertos**: 
	- 22/tcp closed ssh
	- 999/tcp filtered unknown

## Interpretación de los resultados

1. **Puertos Filtered (999)**: Indican que el firewall (UFW) está bloqueando activamente las solicitudes.
2. **Puerto SSH Closed**: SSH no está escuchando conexiones 
3. **OS Detection poco fiable**: el firewall limita la información disponible para fingerprinting

## Comportamiento del escaneo

- **Multiples paquetes SYN**: enviados en rápida sucesión
- **Puertos consecutivos**: escaneados sistemáticamente
- **Respuestas filtered**: timeouts o ICMP unreachable desde el firewall


## Firmas de Nmap identificables

1. **Timing característico**: paquetes enviados en ráfagas
2. **Rango de puertos**: escaneo de puertos comunes (1-1000)
3. **Patrón de reintentos**: múltiples reintentos a puertos filtrados

## Defensas Exitosas

- **UFW Efectivo**: bloqueo proactivo de puertos
- **Detección Temprana**: wireshark identifico el escaneo inmediatamente
- **Exposición Mínima**: Solo información limitada revelada al atacante

## Mejoras Recomendadas

- Implementar mejoras firewall más granulares
- Configurar alertas automáticas para escaneos de puertos
- Considerar utilizar honeypots para engañar a los atacantes
