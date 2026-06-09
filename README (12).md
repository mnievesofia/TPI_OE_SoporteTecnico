# TechBot – Soporte Técnico Nivel 1
### Trabajo Práctico Integrador – Organización Empresarial
**Tecnicatura Universitaria en Programación a Distancia – UTN**

---

## Descripción

Simulación de un proceso administrativo automatizado mediante un chatbot web.  
La organización ficticia **TechSoluciones S.A.** reemplaza su proceso manual de soporte técnico interno por un bot que guía al empleado, consulta una base de datos simulada y registra tickets automáticamente.

El proyecto integra:
- Modelado de procesos con **BPMN 2.0**
- Chatbot web funcional con **máquina de estados**
- Base de datos simulada (empleados + soluciones)
- Manejo de errores y camino infeliz
- Documentación completa en PDF

---

## Archivos del repositorio

| Archivo | Descripción |
|---|---|
| `chatbot_soporte_tecnico.html` | Chatbot completo (HTML + CSS + JS) |
| `bpmn_soporte_tecnico.svg` | Diagrama BPMN 2.0 en formato vectorial |
| `TPI_OE_SoporteTecnico.pdf` | Documentación completa del trabajo |
| `README.md` | Este archivo |

---

## Cómo ejecutar el chatbot

1. Clonar o descargar el repositorio:
```bash
git clone https://github.com/mnievesofia/TPI_OE_SoporteTecnico.git
```

2. Abrir el archivo `chatbot_soporte_tecnico.html` directamente en cualquier navegador web (Chrome, Firefox, Edge).

3. No requiere instalación, servidor, ni conexión a internet.

---

## Cómo usar el bot

1. Ingresá tu número de legajo (4 dígitos)
2. Seleccioná la categoría de tu problema: Hardware / Software / Red
3. Elegí el problema específico de la lista
4. El bot te muestra los pasos de solución
5. Confirmás si se resolvió → se genera el ticket

**Legajos de prueba disponibles:**

| Legajo | Nombre | Área |
|---|---|---|
| 1001 | Ana García | Administración |
| 1002 | Carlos López | Ventas |
| 1003 | María Torres | Sistemas |
| 1004 | Pedro Díaz | Contabilidad |
| 1005 | Laura Fernández | RRHH |

---

## Flujo del proceso (resumen BPMN)

```
[Inicio]
   ↓
[Empleado ingresa legajo] → (validación) → [Error: reintento / deriva a RRHH]
   ↓
[Selecciona categoría: HW / SW / Red]
   ↓
[Selecciona problema específico]
   ↓
[Bot consulta base de datos → muestra solución]
   ↓
¿Se resolvió?
   ├── SÍ → Ticket "Resuelto" → [Fin]
   └── NO → Ticket "Escalado a Técnico N2" → [Fin]
```

---

## Máquina de estados

| Estado | Descripción |
|---|---|
| `ESPERA_LEGAJO` | Solicita y valida el legajo del empleado |
| `ESPERA_CATEGORIA` | Solicita la categoría del problema |
| `ESPERA_PROBLEMA` | Muestra problemas de la categoría seleccionada |
| `ESPERA_RESOLUCION` | Presenta solución y consulta si se resolvió |
| `FINALIZADO` | Ticket cerrado como resuelto |
| `ESCALADO` | Ticket escalado a técnico N2 |

---

## Manejo de errores (camino infeliz)

- Legajo con formato incorrecto → mensaje de error + reintento
- Legajo no encontrado en la base de datos → error + reintento (máximo 3 intentos)
- 3 intentos fallidos → deriva automática a Recursos Humanos
- Entrada de texto libre donde se esperaba una opción → re-muestra las opciones
- Interacción después del cierre del ticket → indica que debe recargar la página

---

## Tecnologías utilizadas

- HTML5 / CSS3 / JavaScript (Vanilla)
- Sin dependencias externas ni frameworks
- Base de datos simulada con objetos JS (JSON)
- BPMN 2.0 para el modelado del proceso

## IA utilizada

Se utilizó **Claude (Anthropic)** como asistente durante el desarrollo: diseño del flujo BPMN, implementación de la máquina de estados, generación del código y redacción de la documentación.

---

## Autora

**Sofia M. Nieves**  
Tecnicatura Universitaria en Programación a Distancia – UTN  
Cátedra: Organización Empresarial  
Docente titular: Prof. Gabriela Martínez
