# IA.md — Uso de Inteligencia Artificial

## Declaración de uso

Durante el desarrollo de este Trabajo Práctico se utilizó el modelo de lenguaje **Claude (Anthropic)** como herramienta de asistencia. A continuación se detalla en qué tareas fue empleado y de qué manera.

| Tarea | Herramienta utilizada | Descripción del uso |
|---|---|---|
| Redacción del archivo `IA.md` | Claude (claude.ai) | Generación de la estructura y contenido de este archivo. |
| Búsqueda de comandos para `estadistica.md` | Claude (claude.ai) | Consulta de los comandos Git necesarios para obtener las estadísticas del repositorio. |

> Todo el contenido generado con asistencia de IA fue revisado, comprendido y validado por los integrantes del equipo antes de ser incorporado al repositorio.

---

## Comandos obtenidos con asistencia de IA

Los siguientes comandos fueron buscados y consultados mediante Claude para completar el archivo `estadistica.md`:

```bash
# Integrante con más commits
git shortlog -sn --all

# Cantidad total de merges
(git log --oneline --merges).Count

# Cantidad de ramas remotas
git branch -r

# Commit con más archivos modificados
git log --stat --oneline

# Ver detalle y diff de un commit específico
git show df01000
```
