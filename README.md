# 🏢 credicel_BD_GRUPO_EMPRESARIAL_EMPRESAL 

¡Bienvenido! 👋 Este repositorio contiene el dump de la base de datos MySQL para el proyecto credicel_BD_GRUPO_EMPRESARIAL_EMPRESAL.

## ⚙️ Descripción

Esta base de datos está diseñada para gestionar información de empleados, novedades (como incapacidades), retiros y vacaciones.  Es una herramienta fundamental para la administración de recursos humanos de Credicel Grupo Empresarial.

## 💾 Estructura de la Base de Datos

La base de datos contiene las siguientes tablas:

*   **`empleados`**:  Información básica de los empleados. 🧑‍💼
*   **`novedades`**:  Registro de novedades e incapacidades de los empleados. 🤕
*   **`retirados`**:  Información sobre los empleados retirados. 🚪
*   **`vacaciones`**:  Gestión de las solicitudes y periodos de vacaciones. 🌴

### `empleados`

| Columna           | Tipo        | Atributos      | Descripción                                                                 |
|-------------------|-------------|----------------|-----------------------------------------------------------------------------|
| `id_empleados`    | INT(11)     | PRIMARY KEY, AUTO_INCREMENT | Identificador único del empleado.                                       |
| `nombre`          | VARCHAR(45) | NOT NULL       | Nombre del empleado.                                                        |
| `apellido`        | VARCHAR(45) | NOT NULL       | Apellido del empleado.                                                      |
| `email`           | VARCHAR(45) | NOT NULL       | Correo electrónico del empleado.                                              |
| `rh`              | VARCHAR(45) | NOT NULL       | Tipo de sangre del empleado.                                                 |
| `edad`            | VARCHAR(45) | NOT NULL       | Edad del empleado.                                                          |

### `novedades`

| Columna                 | Tipo        | Atributos      | Descripción                                                                                                                               |
|-------------------------|-------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| `id_novedad`            | INT(11)     | PRIMARY KEY, AUTO_INCREMENT | Identificador único de la novedad.                                                                                                         |
| `tipo_de_novedad`       | VARCHAR(45) | NOT NULL       | Tipo de novedad (ej: incapacidad, permiso).                                                                                               |
| `dias`                  | VARCHAR(45) | NOT NULL       | Cantidad de días de la novedad.                                                                                                             |
| `fecha_inicio`          | DATE        | NOT NULL       | Fecha de inicio de la novedad.                                                                                                              |
| `fecha_final`           | DATE        |                | Fecha de finalización de la novedad.                                                                                                       |
| `diagnostico`           | VARCHAR(45) |                | Diagnóstico médico (si aplica).                                                                                                              |
| `eps`                   | VARCHAR(45) |                | Entidad Promotora de Salud (EPS).                                                                                                          |
| `empleados_id_empleados`| INT(11)     |                | Clave foránea que relaciona la novedad con el empleado.                                                                                      |

### `retirados`

| Columna                 | Tipo        | Atributos      | Descripción                                                                                 |
|-------------------------|-------------|----------------|---------------------------------------------------------------------------------------------|
| `id_retirado`           | INT(11)     | PRIMARY KEY, AUTO_INCREMENT | Identificador único del retiro.                                                                 |
| `fecha_retiro`          | VARCHAR(45) | NOT NULL       | Fecha de retiro del empleado.                                                                 |
| `novedad`               | VARCHAR(45) | NOT NULL       | Novedad asociada al retiro.                                                                 |
| `motivo_retiro`         | VARCHAR(45) | NOT NULL       | Motivo del retiro.                                                                            |
| `empleados_id_empleados`| INT(11)     | NOT NULL       | Clave foránea que relaciona el retiro con el empleado.                                         |

### `vacaciones`

| Columna                 | Tipo        | Atributos      | Descripción                                                                                 |
|-------------------------|-------------|----------------|---------------------------------------------------------------------------------------------|
| `id_vacaciones`         | INT(11)     | PRIMARY KEY, AUTO_INCREMENT | Identificador único de las vacaciones.                                                              |
| `solicitud`             | VARCHAR(45) | NOT NULL       | Número o referencia de la solicitud de vacaciones.                                          |
| `periodo`               | VARCHAR(45) | NOT NULL       | Periodo al que corresponden las vacaciones.                                                  |
| `fecha_inicio`          | DATE        |                | Fecha de inicio de las vacaciones.                                                          |
| `fecha_final`           | DATE        |                | Fecha de finalización de las vacaciones.                                                      |
| `estado`                | VARCHAR(45) |                | Estado de la solicitud de vacaciones (ej: Pendiente, Aprobada, Rechazada).                   |
| `empleados_id_empleados`| INT(11)     |                | Clave foránea que relaciona las vacaciones con el empleado.                                  |

## 🛠️ Instalación

1.  Asegúrate de tener MySQL instalado.
2.  Crea una base de datos llamada `credicel_BD_GRUPO_EMPRESARIAL_EMPRESAL`.
3.  Importa el archivo `dump.sql` (el que me proporcionaste) a la base de datos.  Puedes usar la línea de comandos o una herramienta como phpMyAdmin.

    ```bash
    mysql -u [usuario] -p credicel_BD_GRUPO_EMPRESARIAL_EMPRESAL < dump.sql
    ```

    Reemplaza `[usuario]` con tu nombre de usuario de MySQL.

## 🤝 Contribución

¡Las contribuciones son bienvenidas!  Si encuentras algún problema o tienes alguna sugerencia, no dudes en abrir un *issue* o enviar un *pull request*.

## 📜 Licencia

Este proyecto no tiene licencia. 😎

## 📧 Contacto

Si tienes alguna pregunta, puedes contactarme a través de [tu correo electrónico] o [tu perfil de LinkedIn].
