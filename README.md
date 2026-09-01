# ** logFilter.sh **


## ⓘ **Descripción**

  - Filtra y consulta direcciones IPv4 con herramientas online y en listas de reputación de amenazas (DNSBL)


## ⚙ **Características**

    ╰─ Extrae las IPv4 del archivo Apache/access.log || lee archivo de IPv4 únicas (-i IPv4_únicas.lst)
    ╰─ Filtra por peticiones maliciosas y país
    ╰─ Consulta a Herramientas Online
    ╰─ Divide las consultas en bloques de (Por defecto: 500 IPs) para rotar la IP con Tor
    ╰─ Lanza consultas en paralelo con xargs/Tor de (Por defecto: 100 hilos) a listas de reputación de amenazas (DNSBL)
    ╰─ Se añaden a listas de baneo si obtienen algún positivo
    ╰─ Refresca a IP de Tor al finalizar cada bloque de IPs


 ☰ **Dependencias:**

    ```bash gawk curl dnsutils bind9-host jq netcat-openbsd dnsutils coreutils tor torsocks xclip
    ```

## 🛠 **Instalación**

1. Dar permisos de ejecución:

   ```bash
    chmod +x logFilter.sh
   ```

2. Ejecutar el script:

   ```bash
    ./logFilter.sh
   ```


**» Uso:**
    `./logFilter.sh [-f LOGFILE] [-i IPV4LST] [-b IP_BLOCK] [-p HILOS] [-c TOOL] [-m] [-h]`

## » **Ejemplos de uso:**

    ```bash
    ./logFilter.sh -f <file.log> [-b <IP_TOR_BLOCK>] [-p <HILOS>]
    ./logFilter.sh -i <IPv4.lst> [-b <IP_TOR_BLOCK>] [-p <HILOS>]
    ./logFilter.sh -f <file.log> -c [api rd dns vt av x]
    ./logFilter.sh -i <IPv4.lst> -c [api rd dns vt av x]
    ./logFilter.sh -f <file.log> -m
    ```
    
