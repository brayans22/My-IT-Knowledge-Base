# Modelos de servicios en la nube de Microsoft: IaaS, PaaS y SaaS

Resumen de los tres modelos de servicio en la nube que ofrece Microsoft (principalmente a través de Azure y Microsoft 365), con ejemplos prácticos de cada uno.

<img width="504" height="176" alt="image" src="https://github.com/user-attachments/assets/379c7f70-80ef-4acc-a2b4-9085d46af909" />

## Tabla comparativa

| Capa | On-premises | IaaS | PaaS | SaaS |
|---|---|---|---|---|
| Aplicaciones | Cliente | Cliente | Microsoft | Microsoft |
| Datos | Cliente | Cliente | Microsoft | Microsoft |
| Runtime | Cliente | Cliente | Microsoft | Microsoft |
| Middleware | Cliente | Cliente | Microsoft | Microsoft |
| Sistema operativo | Cliente | Cliente | Microsoft | Microsoft |
| Virtualización | Cliente | Microsoft | Microsoft | Microsoft |
| Servidores | Cliente | Microsoft | Microsoft | Microsoft |
| Almacenamiento y red | Cliente | Microsoft | Microsoft | Microsoft |

## IaaS — Infraestructura como servicio

Microsoft ofrece la potencia de cálculo: centros de datos, energía, refrigeración y una enorme redundancia. El cliente aloja sus propias máquinas virtuales y sistemas operativos sobre esa infraestructura.

- **Pago**: por uso (CPU, RAM, almacenamiento, red).
- **Tecnología principal**: Azure.
- **Redundancia**: SLA mínimo del 99,9%; en el almacenamiento de Azure puede llegar hasta 15 nueves.
- **Escala**: más de 60 regiones en el mundo, la mayoría con al menos tres centros de datos.
- **Ejemplo**: montar servidores virtuales en Azure en lugar de comprar hardware físico propio.

## PaaS — Plataforma como servicio

Un paso más allá del IaaS: Microsoft también gestiona el sistema operativo y ofrece plataformas y herramientas listas para desarrollar, alojar aplicaciones y gestionar bases de datos.

- **Pago**: mixto (parte por uso, parte por licencia).
- **Ejemplo 1**: Kubernetes, para escalar automáticamente contenedores según la demanda (por ejemplo, un e-commerce que recibe muchas más visitas en rebajas o Navidad).
- **Ejemplo 2**: Microsoft 365 como plataforma base sobre la que corren distintos servicios.
- **Uso típico**: empresas de desarrollo de software que necesitan herramientas de gestión de aplicaciones.

## SaaS — Software como servicio

Microsoft se encarga de todo, incluida la propia aplicación. El cliente paga una licencia para usarla, ya sea en la web o descargada.

- **Pago**: licencia mensual.
- **Ejemplo**: Word, Excel y PowerPoint dentro de Office 365 (también disponibles como aplicaciones descargables, antes llamadas "Pro Plus").
- **Detalle**: si dejas de pagar la licencia, el software se desactiva.

## Nota sobre Office 365 / Microsoft 365

Es un caso híbrido que genera confusión:

- **Microsoft 365** se considera hoy la plataforma **PaaS** principal.
- **Office 365** es una mezcla de PaaS y SaaS, pero si hablamos solo de las aplicaciones (Word, Excel, PowerPoint), es **SaaS**.
