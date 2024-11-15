# Problema: Sistema de Gestión de Hospitales
## Descripción:
Un hospital necesita un sistema básico para gestionar información de pacientes, médicos y citas médicas. El objetivo es crear un CRUD que permita registrar, leer, actualizar y eliminar esta información, garantizando que los datos estén relacionados de forma adecuada.

## Entidades:
### Paciente:

* ID: Identificador único (UUID o Long).
* Nombre: String.
* Apellido: String.
* Fecha de Nacimiento: Date.
* Número de Teléfono: String.
* Correo Electrónico: String.
### Médico:

* ID: Identificador único (UUID o Long).
* Nombre: String.
* Apellido: String.
* Especialidad: String (por ejemplo: Cardiología, Pediatría, etc.).
* Número de Teléfono: String.
* Correo Electrónico: String.
### Cita Médica:

* ID: Identificador único (UUID o Long).
* Fecha y Hora: Date/Time.
* Descripción del Motivo: String.
* Estado: String (Pendiente, Confirmada, Cancelada).
* Paciente: Relación Many-to-One con Paciente.
* Médico: Relación Many-to-One con Médico.
## Funcionalidades:
### Paciente:

* Crear, listar, actualizar y eliminar pacientes.
* Buscar pacientes por nombre o correo electrónico.
### Médico:

* Crear, listar, actualizar y eliminar médicos.
* Buscar médicos por especialidad o nombre.
### Cita Médica:

* Programar una nueva cita asignando un paciente y un médico.
* Actualizar la información de una cita, incluyendo su estado.
* Cancelar una cita.
* Listar todas las citas, filtrarlas por médico, paciente o estado.
## Relación entre Entidades:
* Un Paciente puede tener varias Citas Médicas.
* Un Médico puede tener varias Citas Médicas.
* Una Cita Médica está asociada a un único Paciente y un único Médico.
## Requisitos Técnicos:
* Utiliza Spring Boot con JPA y H2 (o MySQL) como base de datos.
* Expón los endpoints necesarios a través de controladores REST.
* Realiza validaciones básicas (por ejemplo, que no se puedan registrar pacientes sin nombre o citas en el pasado).
* Usa DTOs para las respuestas JSON.
* Configura las relaciones entre las entidades usando anotaciones de JPA (@OneToMany, @ManyToOne, etc.).