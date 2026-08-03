# 📅 AgendaBot

Sistema conversacional desarrollado con **n8n Community Edition**, **Telegram** y **Google Sheets** para gestionar citas, tareas, recordatorios, hábitos y listas mediante una interfaz guiada por menús numéricos.

Este proyecto fue desarrollado como solución al **Proyecto IA Nivel 1** de Campuslands, siguiendo las restricciones y requerimientos establecidos para la implementación de un asistente conversacional sin utilizar servicios de pago, modelos de IA entrenados ni bases vectoriales.

---

# 🎯 Objetivo

Desarrollar un asistente conversacional capaz de organizar información personal mediante flujos automatizados, utilizando únicamente herramientas gratuitas y permitidas por el proyecto.

El bot permite administrar:

- 📅 Citas
- ✅ Tareas
- 🔔 Recordatorios
- 💪 Hábitos
- 📝 Listas
- 📊 Reportes
- 👤 Usuarios y permisos

Todo el estado conversacional es administrado mediante Google Sheets y automatizado con n8n.

---

# 🛠 Tecnologías utilizadas

- Telegram Bot API
- n8n Community Edition
- Google Sheets
- JavaScript

---

# ⚙️ Funcionalidades implementadas

## Gestión de Agenda

- Crear citas
- Consultar agenda
- Reprogramar citas
- Cancelar citas
- Marcar citas como completadas

## Gestión de Tareas

- Crear tareas
- Consultar tareas
- Actualizar estado

## Gestión de Recordatorios

- Crear recordatorios
- Consultar recordatorios

## Gestión de Hábitos

- Registrar hábitos
- Consultar hábitos

## Gestión de Listas

- Crear listas
- Agregar ítems
- Consultar listas

## Reportes

- Resumen de citas

## Configuración

- Actualización del nombre del usuario

## Administración

- Consulta de usuarios
- Registro de usuarios
- Cambio de permisos

## Automatizaciones

- Router principal por pantalla
- Gestión del estado conversacional (Sessions)
- Registro automático de Logs
- Resumen diario mediante Schedule

---

# 🗂 Modelo de datos

El proyecto utiliza un documento de Google Sheets denominado **AgendaBot_DB**, compuesto por las siguientes hojas:

- CITAS
- TAREAS
- RECORDATORIOS
- HABITOS
- LISTAS
- ITEMS_LISTA
- USUARIOS
- LOGS
- SESSIONS

---

# 📁 Estructura del repositorio

```text
Proyecto_IA_Nivel1_AguileraFabian/
│
├── README.md
├── docs/
│   └── AgendaBot.md
├── workflows/
│   └── AgendaBot_Workflow.json
└── evidencias/
```

---

# 🚀 Ejecución

1. Importar el workflow ubicado en:

```
workflows/AgendaBot_Workflow.json
```

2. Configurar las credenciales de:

- Telegram
- Google Sheets

3. Crear el documento **AgendaBot_DB** con las hojas especificadas en el proyecto.

4. Activar el workflow en n8n.

5. Iniciar conversación con el bot desde Telegram.

---

# 📸 Evidencias

Las capturas de funcionamiento del proyecto se encuentran en la carpeta:

```
evidencias/
```

---

# 👨‍💻 Autor

**Fabián Aguilera**

Proyecto desarrollado para el curso **Proyecto IA Nivel 1** - Campuslands.
