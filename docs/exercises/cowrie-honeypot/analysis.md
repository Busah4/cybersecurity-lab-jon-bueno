# Cowrie Honeypot - Analysis

## 1. Objetivo

El propósito de este ejercicio fue **instalar, configurar y analizar un honeypot Cowrie** dentro del entorno del *home lab* personal, con el objetivo de observar intentos de conexión y actividad sospechosa de atacantes automatizados en una máquina virtual controlada.

Cowrie es un honeypot de tipo *medium-interaction* diseñado para emular servicios como **SSH** y **Telnet**, permitiendo registrar intentos de intrusión, comandos ejecutados y credenciales utilizadas.

## 2. Entorno y configuración

- **Sistema operativo:** Ubuntu Server (VirtualBox VM)
- **Red:** NAT Network (dirección IP interna `10.0.2.15`)
- **Honeypot:** Cowrie (instalado en `/home/cowrie/cowrie/`)
- **Logs almacenados en:** `/home/cowrie/cowrie/var/log/cowrie/cowrie.log`
- **Versión:** Cowrie 2.x
- **Usuario de ejecución:** `cowrie`

La red utilizada es completamente **aislada del entorno real**, por lo que las direcciones IP capturadas en los registros corresponden a la red virtual y no a direcciones públicas, eliminando cualquier riesgo de exposición de información sensible.

## 3. Actividad registrada

Durante el período de observación, Cowrie registró múltiples intentos de conexión simulados. 
En el archivo `cowrie.log` se pueden observar las siguientes entradas destacadas:

```text
2025-11-02T14:52:33+0000 [SSHService ssh-userauth on HoneyPotTransport,0,10.0.2.2] login attempt [root/123456]
2025-11-02T14:52:34+0000 [SSHService ssh-userauth on HoneyPotTransport,0,10.0.2.2] login failed [root/123456]
2025-11-02T14:53:12+0000 [SSHService ssh-userauth on HoneyPotTransport,1,10.0.2.3] login attempt [admin/admin]
2025-11-02T14:53:13+0000 [SSHService ssh-userauth on HoneyPotTransport,1,10.0.2.3] login failed [admin/admin]
2025-11-02T14:55:10+0000 [CowrieTelnetTransport,2,10.0.2.4] login attempt [pi/raspberry]

