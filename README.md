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
## 📊 Nueva funcionalidad: Reporte de productividad por usuario

Como parte de la evolución de AgendaBot, se incorporó una nueva opción dentro del menú **Reportes** que permite generar un resumen de productividad de los usuarios registrados en el sistema.

### Acceso

Desde Telegram:

```text
Menú principal
└── 6. Reportes
    └── 6. Productividad por usuario (reporte completo)
```

Al seleccionar esta opción, el bot informa que está generando el reporte y posteriormente envía un resumen de productividad directamente en el chat.

### Información utilizada

El reporte se construye leyendo la información almacenada en Google Sheets desde las siguientes hojas:

- CITAS
- TAREAS
- LOGS
- USUARIOS

### Métricas calculadas

Para cada usuario se calculan los siguientes indicadores:

- Total de citas registradas.
- Citas completadas.
- Citas canceladas.
- Total de tareas.
- Tareas completadas.
- Tareas pendientes.
- Total de interacciones con el bot.

Además, se presenta un resumen general con:

- Usuario más activo.
- Total de citas registradas.
- Total de tareas registradas.
- Total de interacciones con AgendaBot.

### Validaciones implementadas

Durante la generación del reporte se aplican las siguientes reglas:

- Los registros incompletos son ignorados.
- Los usuarios sin citas o tareas se muestran con valores en cero.
- Los usuarios se presentan ordenados por su identificador de Telegram.
- La consulta no modifica la información almacenada en Google Sheets.

### Flujo de ejecución

```text
Telegram
      │
      ▼
Menú Reportes
      │
      ▼
Productividad por usuario
      │
      ▼
Lectura de USUARIOS
      │
      ▼
Lectura de CITAS
      │
      ▼
Lectura de TAREAS
      │
      ▼
Lectura de LOGS
      │
      ▼
Cálculo de indicadores
      │
      ▼
Generación del reporte
      │
      ▼
Envío del reporte por Telegram
```

### Evidencias

La implementación de esta funcionalidad se encuentra documentada en la carpeta **evidencias**, incluyendo:

- Menú de Reportes actualizado.
- Mensaje de inicio de generación del reporte.
- Reporte de productividad mostrado en Telegram.
- Registro de la ejecución en la hoja LOGS.
---

# 👨‍💻 Autor

**Fabián Aguilera**

Proyecto desarrollado para el curso **Proyecto IA Nivel 1** - Campuslands.
