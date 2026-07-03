# AlkeWallet — Diseño e Implementación de Base de Datos Relacional

![AlkeWallet Logo](./Diagrama/diagrama.png)

## 📋 Descripción del Proyecto

AlkeWallet es una base de datos relacional diseñada para gestionar un monedero virtual. Permite administrar usuarios, monedas y transacciones de forma segura, garantizando la integridad de los datos mediante restricciones ACID y validaciones de integridad referencial.

Este proyecto incluye:
- ✅ Modelo Entidad-Relación (MER)
- ✅ Scripts DDL para creación de tablas
- ✅ Sentencias DML para manipulación de datos
- ✅ Consultas SQL avanzadas con JOINs y agregaciones
- ✅ Validación de transacciones ACID
- ✅ Vistas y análisis de datos

---

## 📁 Estructura del Proyecto

### 📊 Diagrama
- **[Diagrama/](./Diagrama/)** — Modelo Entidad-Relación de la base de datos

### 🗄️ 3. Script DDL — Creación de la Base de Datos
- **[Creacion y selección de la base de datos/](./Screenshots/3.%20Script%20DDL%20-%20Creación%20de%20la%20base%20de%20datos/Creacion%20y%20selección%20de%20la%20base%20de%20datos/)** — Comandos para crear la base de datos y tablas
- **[Creacion Tablas/](./Screenshots/3.%20Script%20DDL%20-%20Creación%20de%20la%20base%20de%20datos/Creacion%20Tablas/)** — Definición de tablas (USUARIO, MONEDA, TRANSACCION)
- **[Verificacion/](./Screenshots/3.%20Script%20DDL%20-%20Creación%20de%20la%20base%20de%20datos/Verificacion/)** — Scripts de verificación de la estructura

### 💾 4. Sentencias DML — Carga y Manipulación de Datos
- **[4.1 Inserción de datos de prueba/](./Screenshots/4.%20Sentencias%20DML%20-%20Carga%20y%20manipulacion%20de%20datos/4.1%20Inserción%20de%20datos%20de%20prueba/)** — INSERT de usuarios, monedas y transacciones
- **[4.2 Transacción controlada (ACID) — actualización de saldo/](./Screenshots/4.%20Sentencias%20DML%20-%20Carga%20y%20manipulacion%20de%20datos/4.2%20Transacción%20controlada%20(ACID)%20%E2%80%94%20actualización%20de%20saldo/)** — Transacciones ACID con COMMIT/ROLLBACK
- **[4.3 Simulación de error de integridad referencial y ROLLBACK/](./Screenshots/4.%20Sentencias%20DML%20-%20Carga%20y%20manipulacion%20de%20datos/4.3%20Simulación%20de%20error%20de%20integridad%20referencial%20y%20ROLLBACK/)** — Validación de FK con ROLLBACK
- **[4.5 Sentencia DML — modificar correo electrónico/](./Screenshots/4.%20Sentencias%20DML%20-%20Carga%20y%20manipulacion%20de%20datos/4.5%20Sentencia%20DML%20%E2%80%94%20modificar%20correo%20electrónico/)** — UPDATE de datos
- **[4.6 Sentencia DML — eliminar una transacción/](./Screenshots/4.%20Sentencias%20DML%20-%20Carga%20y%20manipulacion%20de%20datos/4.6%20Sentencia%20DML%20%E2%80%94%20eliminar%20una%20transacción/)** — DELETE de registros

### 🔍 5. Consultas SQL (SELECT)
- **[5.1 Nombre de la moneda elegida por un usuario específico/](./Screenshots/5.%20Consultas%20SQL%20(SELECT)/5.1%20Nombre%20de%20la%20moneda%20elegida%20por%20un%20usuario%20específico/)** — SELECT con INNER JOIN
- **[5.2 Todas las transacciones registradas/](./Screenshots/5.%20Consultas%20SQL%20(SELECT)/5.2%20Todas%20las%20transacciones%20registradas/)** — Listado completo de transacciones
- **[5.3 Transacciones realizadas por un usuario específico/](./Screenshots/5.%20Consultas%20SQL%20(SELECT)/5.3%20Transacciones%20realizadas%20por%20un%20usuario%20específico/)** — Consulta con CASE WHEN
- **[5.4 Consultas adicionales (Lección 2 — JOIN, WHERE, agregaciones)/](./Screenshots/5.%20Consultas%20SQL%20(SELECT)/5.4%20Consultas%20adicionales%20(Lección%202%20%E2%80%94%20JOIN,%20WHERE,%20agregaciones)/)** — Ejemplos avanzados de SELECT
- **[Tarea Plus — vista con el top-5 de usuarios con mayor saldo/](./Screenshots/5.%20Consultas%20SQL%20(SELECT)/Tarea%20Plus%20%E2%80%94%20vista%20con%20el%20top-5%20de%20usuarios%20con%20mayor%20saldo/)** — Vistas (VIEW) y rankings

---

## 🏗️ Modelo Entidad-Relación

### Entidades y Relaciones

| Entidad | Descripción | Clave Primaria |
|---------|-------------|---|
| **usuario** | Usuarios del monedero virtual | `user_id` (AUTO_INCREMENT) |
| **moneda** | Monedas disponibles | `currency_id` (AUTO_INCREMENT) |
| **transaccion** | Transacciones entre usuarios | `transaction_id` (AUTO_INCREMENT) |

### Relaciones

- **Usuario ↔ Moneda** (N:1): Un usuario tiene una moneda preferida; una moneda puede ser elegida por múltiples usuarios
- **Usuario ↔ Transaccion** (1:N): Un usuario puede enviar y recibir múltiples transacciones
- **Moneda ↔ Transaccion** (1:N): Una moneda puede estar asociada a múltiples transacciones

---

## 📝 Propiedades ACID Implementadas

| Propiedad | Implementación |
|-----------|---|
| **Atomicidad** | Transacciones de transferencia como unidad indivisible |
| **Consistencia** | Restricciones (FK, NOT NULL, CHECK) |
| **Aislamiento** | Nivel de aislamiento en base de datos |
| **Durabilidad** | Confirmación permanente con COMMIT |

---

## 🔧 Cómo Usar

1. **Crear la base de datos:** Ejecuta el script DDL de [Creacion y selección de la base de datos/](./Screenshots/3.%20Script%20DDL%20-%20Creación%20de%20la%20base%20de%20datos/Creacion%20y%20selección%20de%20la%20base%20de%20datos/)
2. **Cargar datos de prueba:** Ejecuta el script DML de [4.1 Inserción de datos de prueba/](./Screenshots/4.%20Sentencias%20DML%20-%20Carga%20y%20manipulacion%20de%20datos/4.1%20Inserción%20de%20datos%20de%20prueba/)
3. **Realizar consultas:** Usa los archivos en [5. Consultas SQL (SELECT)/](./Screenshots/5.%20Consultas%20SQL%20(SELECT)/)

---

## 📚 Concepto de Base de Datos Relacional

Una base de datos relacional organiza la información en **tablas** (relaciones) compuestas por **filas** (registros) y **columnas** (atributos), vinculadas mediante **claves primarias** y **claves foráneas**.

### Ventajas

✅ Integridad referencial garantizada  
✅ Consistencia mediante restricciones  
✅ Lenguaje SQL estándar  
✅ Soporte para transacciones ACID  
✅ Normalización (reducción de redundancia)

---

## 📄 Documentación Completa

Para obtener información detallada sobre el diseño, implementación y validación del proyecto, consulta:
- [Alke Wallet - Entregable.md](./Alke%20Wallet%20-%20Entregable.md)

---

## 👤 Autor

Proyecto desarrollado como parte del **Módulo #5** de la Especialización en Desarrollo Full Stack.

---

**Última actualización:** Julio 2026