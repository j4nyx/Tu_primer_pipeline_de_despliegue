#Added: cosas nuevas. 
#Change: cambios en cómo funciona algo que ya existía.
#Fixed: errores o fallos que fueron corregidos.
#Removed: funcionalidades eliminadas.


# Changelog
Todos los cambios notables de este proyecto se documentarán en este archivo.

El formato está basado en [Keep a Changelog](https://keepachangelog.com/es-ES/1.0.0/),  
y este proyecto sigue [Semantic Versioning](https://semver.org/lang/es/).

---

## [Unreleased]
### Added
- Funcionalidad de exportar reportes en PDF.
- Soporte para autenticación con Google.

### Changed
- Mejora en el rendimiento de las consultas a la base de datos.
- Actualización de dependencias de Spring Boot 3.2.1 a 3.2.3.

### Fixed
- Error al calcular el total de ventas con descuentos negativos.
- Bug en la validación de correos electrónicos.

---

## [1.1.0] - 2025-09-01
### Added
- Endpoint `/api/ventas` para registrar ventas.
- Documentación interactiva con Swagger UI.
- Tests unitarios en la capa de servicios.

### Changed
- Reorganización de la estructura de paquetes (`controller`, `service`, `repository`).
- Estandarización de logs con SLF4J.

---

## [1.0.0] - 2025-08-15
### Added
- Versión inicial de la aplicación.
- API REST para gestión de usuarios.
- Conexión a base de datos Oracle.
