# Cloud Deployment Models: Public, Private And Hybrid

## Public Cloud

**Definición**
- Proveedor de nube abierto al público (ej. Microsoft Azure).
- El cliente es un "inquilino" que comparte el hardware físico con otros inquilinos.

**Aislamiento y seguridad**
- El software y los datos de cada inquilino permanecen privados entre sí.
- Existe conectividad **B2B** (Business to Business) para permitir intercambio controlado entre organizaciones cuando se necesita.

**Analogía**
- Como alquilar un apartamento: servicios propios (agua, luz) + zonas comunes compartidas (piscina, parque) con otros inquilinos del complejo.

**Ventajas**
- Menor coste (no hay que comprar hardware/software propio).
- Sin mantenimiento (el proveedor gestiona el hardware).
- Escalabilidad casi ilimitada.
- Alta fiabilidad y redundancia (Microsoft: ~70 regiones, ~3 centros de datos por región).

## Private Cloud

**Definición**
- Todo el equipo está dedicado en exclusiva a una sola empresa u organización.

**Modalidades de alojamiento**
- Centros de datos propios de la organización.
- Proveedor externo con hardware dedicado (ej. Microsoft + Departamento de Defensa de EE.UU.).

**Perfil típico de uso**
- Agencias gubernamentales.
- Instituciones financieras.
- Organizaciones con altos requisitos de control y cumplimiento.

**Ventajas**
- Más flexibilidad (el equipo es solo tuyo).
- Más control (recursos no compartidos).
- Más seguridad (sin otros clientes en el mismo hardware).
- Buena escalabilidad (no compites por hardware con terceros).

**Desventaja principal**
- Coste mucho más alto (hardware dedicado o infraestructura propia).

## Hybrid Cloud

**Definición**
- Combinación de infraestructura local (on-premises) o nube privada junto con nube pública.
- Permite decidir qué recursos van en cada entorno.

**Contexto**
- Modelo donde se encuentra la mayoría de las empresas hoy en día, producto de la migración progresiva desde entornos 100% on-premises.

**Ventajas**
- **Flexibilidad**: elegir qué queda local y qué se mueve a la nube, y cuándo.
- **Control de datos sensibles**: mantener infraestructura privada por motivos de sensibilidad o normativa.
- **Escalabilidad bajo demanda**: ej. servidores web locales que escalan a la nube pública cuando crece la carga.
- **Rentabilidad**: se evita el gasto recurrente en hardware y licencias on-premises.
- **Transición facilitada**: Microsoft ofrece herramientas de migración progresiva.

**Ejemplos de migración típica**
- Exchange Server (on-premises) → Exchange Online.
- Archivos locales → SharePoint / OneDrive.
- Skype for Business (servidor) → Microsoft Teams.
- SharePoint on-premises → SharePoint Online.

**Caso concreto**
- Empresas que dejan de comprar servidores y licencias de Exchange cada pocos años y migran su correo a Exchange Online (ej. caso real de un hospital que abandonó Exchange on-premises).
