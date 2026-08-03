# AgendaBot

## Proyecto IA Nivel 1

**Autor:** Fabián Aguilera

---

# 1. Introducción

AgendaBot es un asistente conversacional desarrollado utilizando **Telegram**, **n8n Community Edition** y **Google Sheets**, cuyo objetivo es facilitar la gestión de citas, tareas, recordatorios, hábitos y listas mediante una conversación guiada por menús numéricos.

El proyecto fue desarrollado siguiendo las restricciones establecidas para el Proyecto IA Nivel 1, utilizando únicamente herramientas gratuitas y sin depender de servicios de inteligencia artificial de pago.

---

# 2. Arquitectura del sistema

El sistema está compuesto por tres componentes principales:

```
Usuario
   │
   ▼
Telegram
   │
   ▼
n8n Community Edition
   │
   ▼
Google Sheets
```

### Telegram

Actúa como interfaz conversacional entre el usuario y el sistema.

### n8n

Centraliza toda la lógica del proyecto:

- Gestión de sesiones
- Navegación por menús
- Validaciones
- Automatizaciones
- Actualización de datos
- Generación de respuestas

### Google Sheets

Funciona como base de datos del sistema almacenando toda la información generada por los usuarios.

---

# 3. Modelo de datos

El documento **AgendaBot_DB** contiene las siguientes hojas:

| Hoja | Descripción |
|------|-------------|
| CITAS | Información de las citas registradas |
| TAREAS | Gestión de tareas |
| RECORDATORIOS | Recordatorios del usuario |
| HABITOS | Hábitos registrados |
| LISTAS | Listas creadas por el usuario |
| ITEMS_LISTA | Elementos de cada lista |
| USUARIOS | Usuarios autorizados |
| LOGS | Registro de interacciones |
| SESSIONS | Estado conversacional |

---

# 4. Funcionalidades implementadas

## Agenda

- Crear citas
- Consultar agenda
- Reprogramar citas
- Cancelar citas
- Completar citas

## Tareas

- Crear tareas
- Consultar tareas
- Actualizar estado

## Recordatorios

- Registrar recordatorios
- Consultar recordatorios

## Hábitos

- Registrar hábitos
- Consultar hábitos

## Listas

- Crear listas
- Agregar elementos
- Consultar listas

## Reportes

- Resumen de citas registradas

## Configuración

- Actualización del nombre del usuario

## Administración

- Consulta de usuarios
- Registro de nuevos usuarios
- Cambio de permisos

---

# 5. Gestión del estado conversacional

El proyecto implementa una máquina de estados utilizando la hoja **SESSIONS**.

Cada usuario conserva:

- Pantalla actual
- Paso actual
- Datos parciales
- Última interacción

Esto permite que el usuario pueda continuar un flujo sin perder el contexto de la conversación.

---

# 6. Validaciones implementadas

Durante el desarrollo se implementaron las siguientes validaciones:

- Validación de opciones según el menú actual.
- Validación del formato de fecha.
- Validación del formato de hora.
- Restricción para registrar citas en fechas pasadas.
- Verificación para evitar doble reserva de citas.
- Confirmación antes de guardar una cita.
- Control de acceso mediante permisos de usuario.

---

# 7. Automatizaciones implementadas

El workflow implementa las siguientes automatizaciones:

- Router principal por pantalla.
- Flujo guiado para creación de citas.
- Gestión del estado de tareas.
- Registro automático de logs.
- Resumen diario mediante Schedule Trigger.

---

# 8. Flujo general del sistema

```
Telegram
      │
      ▼
Validación del usuario
      │
      ▼
Recuperación de sesión
      │
      ▼
Procesamiento de la lógica principal
      │
      ▼
Router por acción
      │
      ▼
Google Sheets
      │
      ▼
Respuesta al usuario
```

---

# 9. Evidencias

Las evidencias del funcionamiento del proyecto se encuentran almacenadas en la carpeta:

```
evidencias/
```

Estas incluyen capturas del funcionamiento de:

- Agenda
- Tareas
- Recordatorios
- Hábitos
- Listas
- Reportes
- Administración
- Registro de Logs
- Resumen diario

---

# 10. Conclusiones

El desarrollo de AgendaBot permitió integrar Telegram, n8n y Google Sheets para construir un asistente conversacional capaz de administrar información mediante flujos automatizados.

La implementación de una máquina de estados, un router principal y un modelo de datos estructurado permitió desarrollar un sistema modular, organizado y fácil de mantener, cumpliendo con los requerimientos establecidos para el Proyecto IA Nivel 1.
