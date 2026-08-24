# Fundamentos de dominios Microsoft: Active Directory, DNS y GPOs

Resumen de los conceptos clave para entender la gestión de entornos Microsoft on-premise: de las redes peer-to-peer a la centralización con Active Directory, autenticación, resolución de nombres y políticas de grupo.

## De los mainframes a las redes peer-to-peer

- **Años 50-60**: mainframes gigantes con tubos de vacío.
- **Años 70**: aparece el circuito integrado (CI), que permite la informática personal.
- **Años 80**: las empresas empiezan a comprar PCs, conectados en redes **peer to peer** (sin centralización).
  - **Problema**: cada máquina era "su propio jefe". Un administrador tenía que sentarse en cada ordenador para hacer cambios, y compartir archivos requería conocer contraseñas ajenas. Ineficiente.

## La centralización: de Novell a Active Directory

- **Novell (años 90)**: con su producto **NetWare**, introduce el concepto de servidor de archivos para compartir archivos de forma centralizada.
- **Microsoft NT**: crea el concepto de **controlador de dominio** (un servidor especial que gestiona otros servidores/máquinas).
- **Año 2000**: Microsoft lanza **Active Directory (AD)**, representado con un triángulo. Sigue llamándose hoy "Servicios de dominio Active Directory" (AD DS), lo cual indica que es un dominio **on-premise**.

## Cómo funciona un controlador de dominio

Es un servidor con una base de datos (representada como un cilindro) que almacena los objetos del dominio (usuarios, equipos, etc.).

**Por qué tener varios controladores de dominio:**
- **Reparto de carga**: evita saturar un único servidor con autenticaciones.
- **Redundancia**: si uno cae, el otro sigue funcionando.

**Replicación**: todo lo creado en un controlador (por ejemplo, una cuenta de usuario) se replica automáticamente en los demás. Así, un usuario puede autenticarse desde cualquier máquina del dominio.

**Protocolos de autenticación:**
- **Kerberos**: el protocolo moderno y estándar actual.
- **NTLM**: protocolo legado, usado antes del año 2000.

**Lenguaje de directorio**: **LDAP** (Protocolo Ligero de Acceso a Directorios), algo anticuado pero todavía funcional y seguro.

## DNS: el "traductor" de nombres a direcciones

- Cada dominio necesita un nombre (normalmente el de la empresa, ej. `pruebaslab.com`).
- El **servidor DNS** traduce nombres de máquina a direcciones IP, con su propia base de datos (DNS database).
- **Ejemplo práctico**: un cliente necesita autenticarse → pregunta al DNS dónde está el controlador de dominio → DNS responde con la IP → el cliente se autentica.
- Todas las máquinas (controladores de dominio, servidores de archivos, clientes) se registran en el DNS, centralizando la resolución de nombres.

## GPOs: gestión centralizada de configuraciones

Los **Objetos de Directiva de Grupo (GPO)** permiten aplicar configuraciones a muchas máquinas a la vez.

- **Ejemplos de uso**: activar firewalls obligatoriamente, forzar actualizaciones de antivirus, bloquear fondos de pantalla personalizados, incluso desplegar software.
- Igual que las cuentas de usuario, **los GPOs también se replican** entre controladores de dominio.

## El dominio tradicional frente a Internet

- La red interna se conecta a Internet a través de un **firewall**, que protege el tráfico entrante y permite solo lo autorizado.
- Este es el modelo de dominio "tradicional" que se ha usado durante 20 años — la base sobre la que luego se construyen conceptos más modernos como VPN, RADIUS y virtualización.
