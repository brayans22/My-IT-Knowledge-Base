# Microsoft 365 Licensing And Subscriptions

## Suscripciones Vs Licencias

- **Suscripción**: lo que se paga mensualmente (ej. Microsoft 365 E5).
- **Licencia**: unidad individual comprada dentro de esa suscripción, que se asigna a un usuario.
- **Dónde gestionarlo**: `admin.microsoft.com` → **Facturación > Licencias**.
- **Dónde comprarlas**: Marketplace o Servicios de Compra de Facturación, según la región.

## SKU Y Niveles De Producto

- **SKU (Stock Keeping Unit)**: cada tipo de licencia; desbloquea un conjunto distinto de funciones.
- **Microsoft 365 E5**: nivel más completo, incluye la mayoría de funciones (también el más caro).
- **Microsoft 365 E3**: nivel intermedio, menos funciones que E5.
- **Microsoft 365 F3**: pensado para *frontline workers* (trabajadores sin equipo fijo, tipo quiosco).
- Es posible **comparar SKUs** entre sí en el Marketplace antes de comprar.

## Servicios Que Desbloquea Una Licencia

- Microsoft Teams
- Exchange Online (correo)
- SharePoint
- OneDrive
- Intune
- Defender
- Entra ID Premium (antes Azure AD Premium)

## Reglas De Asignación

- **Sin licencia = sin acceso**: el usuario puede iniciar sesión pero no usar ningún servicio.
- **Asignación individual**: una licencia por usuario, manual.
- **Asignación por grupo**: asignar la licencia a un grupo la reparte automáticamente entre todos sus miembros; simplifica la gestión a gran escala.

## Comportamiento Dinámico De Las Licencias

- **Cambio de grupo**: si un usuario cambia de grupo (ej. de Ventas a Marketing), pierde las licencias del grupo anterior y hereda las del nuevo automáticamente.
- **Conflicto de licencias**: si un usuario está en varios grupos con la misma SKU, solo consume **una** licencia (no se duplica).
- **SKU más alta prevalece**: si un usuario pertenece a grupos con SKUs distintas, hereda las funciones de la SKU más completa.
- **Desactivación selectiva**: se puede quitar acceso a un servicio concreto (ej. Teams) sin afectar al resto de la licencia.

## Dependencias Entre Licencias

- Algunas funciones requieren licencias adicionales específicas — ej. **acceso condicional** necesita **Entra ID Premium P1**.
- Las suscripciones grandes (como E5) suelen **incluir automáticamente** estas licencias adicionales, sin coste extra.
- **Nota de nomenclatura**: Microsoft renombró **Azure Active Directory** a **Entra ID**, pero aún aparece con el nombre antiguo en partes de la consola.

## Seguridad Y Cumplimiento

- **Protección de información**: cifrado de datos incluido en ciertas licencias.
- **Autenticación multifactor (MFA)**: soporte para reconocimiento facial, apps autenticadoras, etc.
- **Al quitar una licencia**: se pierde el acceso a los datos asociados a ese servicio (correo, OneDrive, Teams...).
