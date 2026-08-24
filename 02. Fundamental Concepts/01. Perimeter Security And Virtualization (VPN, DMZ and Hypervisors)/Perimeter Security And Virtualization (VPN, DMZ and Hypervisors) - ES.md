# Perimeter Security And Virtualization: VPN, DMZ And Hypervisors

Resumen de cómo las empresas conectaban de forma segura a usuarios remotos, exponían servicios a Internet sin comprometer la red interna, y cómo la virtualización sentó las bases de la computación en la nube.

<img width="644" height="352" alt="image" src="https://github.com/user-attachments/assets/c69f6e2c-e6aa-4089-b126-97aff3c066bf" />

## The Remote Access Problem

Con el trabajo desde casa cada vez más habitual, los usuarios necesitan acceder a servicios internos (servidor de archivos, SQL, Microsoft Exchange, SharePoint) sin estar físicamente en la oficina.

**Lo que no se debe hacer**: abrir todos los puertos del firewall para permitir acceso externo sin seguridad. En los años 90 muchas empresas lo hacían (incluso sin firewall), exponiendo la red directamente a **hackers** que buscan robar datos o lanzar ataques de ransomware.

## VPN And The RAS Server

La solución tradicional para el acceso remoto seguro:

- **VPN (Virtual Private Network)**: crea un "túnel" de comunicaciones cifradas.
- **Concentrador VPN**: dispositivo dedicado a gestionar estas conexiones seguras.
- **Servidor RAS (Routing and Remote Access Services)**: en el mundo Microsoft, es el servidor que da soporte a las conexiones VPN y permite el acceso remoto a los recursos internos.

**Cómo protege**: un hacker que intercepte el tráfico solo verá que alguien se conecta al firewall, pero no podrá ver el contenido, ya que todo el tráfico va cifrado a través del túnel VPN.

## Exposing A Web Server To The Internet

Si una empresa aloja su propio servidor web (por ejemplo, `www.pruebaslab.com`) accesible de forma anónima desde Internet, surgen dos riesgos:

1. **Alojarlo dentro del dominio**: obligaría a abrir los puertos 80 (HTTP) y 443 (HTTPS) en el firewall interno, permitiendo entrar tanto a usuarios legítimos como a hackers.
2. **Pivotaje**: si un hacker compromete el servidor web alojado internamente, puede usarlo como puente para acceder a otros servicios de la red interna.

## The Solution: DMZ / Perimeter Network

Para evitar estos riesgos, se usan **dos firewalls**:

- **Firewall interno**: protege la red interna (dominio, servidores de archivos, SQL, etc.).
- **Firewall externo**: protege frente a Internet.
- **DMZ (zona desmilitarizada)** o **red perimetral**: la red intermedia entre ambos firewalls, donde se coloca el servidor web.

**Cómo funciona**:
- Solo se abren los puertos estrictamente necesarios (ej. 443, 53 para DNS) hacia la DMZ.
- Si el servidor web de la DMZ es hackeado, el firewall interno impide que el ataque llegue a los recursos internos.
- El único tráfico permitido hacia dentro suele ser el de la VPN, con su propia autenticación.

## Virtualization: The Origin Of The Cloud

Tradicionalmente cada servicio (archivos, SQL, Exchange, SharePoint) requería su propio servidor físico dedicado — y para tener redundancia, el doble de servidores.

- **Hipervisor**: software que emula hardware, permitiendo ejecutar varios sistemas/servidores virtuales sobre una sola máquina física. El concepto existe desde los años 70 (los mainframes ya repartían tiempo de procesamiento).
- **VMware**: la empresa que más impulsó y popularizó la virtualización moderna.
- **Hyper-V**: el hipervisor de Microsoft (Microsoft no inventó el concepto, pero desarrolló su propia solución).

**Ventajas de la virtualización**:
- **Consolidación**: un solo servidor físico potente puede alojar varios servidores virtuales, reduciendo la necesidad de hardware redundante (de 8 servidores físicos a, por ejemplo, 2).
- **Puntos de control (snapshots)**: permiten volver atrás si algo sale mal tras un cambio.
- **Redundancia simplificada**: basta con tener una copia de las máquinas virtuales en un segundo servidor físico.
- **Elasticidad**: los recursos (RAM, CPU) se agrupan en un "pool" compartido. Si un servidor virtual no usa toda su RAM asignada, puede cederla temporalmente a otro que la necesite, y devolverla después.

Esta elasticidad, aplicada a gran escala en múltiples máquinas dentro de centros de datos, es la base sobre la que se construye la computación en la nube.
