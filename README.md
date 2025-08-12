# Mosiah_MT
recoup-proyecto/                ← nombre del repo (recoup-proyecto)
├─ README.md
├─ .gitignore
├─ requirements.txt
├─ src/
│  └─ main.py
├─ docs/
│  └─ diagramas/
│     └─ flujo_funcionalidad_1.mmd
└─ entrega/
   └─ avance_codigo.txt
# Proyecto: Sistema Recoup - Avance

**Alumno:** <<Mosiah Torres>>  
**Asignatura:** <<Logica de programacion>>  
**Fecha del avance:** <<12 agosto 2025>>

## Objetivo del repositorio
Este repositorio contiene el avance inicial para el proyecto de la clínica Recoup: preparación del ambiente, diagramas de flujo y un prototipo mínimo de código para comenzar la etapa de codificación.

## Contenido
- `src/main.py` : archivo de inicio con funciones de ejemplo.
- `docs/diagramas/flujo_funcionalidad_1.mmd` : diagrama de flujo en formato Mermaid (puedes visualizarlo en GitHub).
- `requirements.txt` : dependencias mínimas.
- `entrega/avance_codigo.txt` : descripción del avance entregado.

## Instrucciones para el profesor
1. Revisar `docs/diagramas/flujo_funcionalidad_1.mmd` para ver el diagrama de la funcionalidad principal.
2. Ejecutar `src/main.py` para probar el prototipo (requiere Python 3.8+).
3. Comentarios y retroalimentación en la sección de Issues o por correo.

## Próximos pasos
- Implementación completa de módulos de red y VLAN en el prototipo.
- Documentación del diseño de subredes (VLSM).
- Implementación en Cisco Packet Tracer (archivo aparte).

---
# Python
__pycache__/
*.pyc
*.pyo
.env
venv/
.env/
.idea/
.vscode/
"""
Prototipo inicial del sistema Recoup.
Ejecuta: python src/main.py
"""

from datetime import datetime

def saludo_inicial(nombre="Estudiante"):
    ahora = datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    return f"Hola {nombre}, este es un prototipo inicial. Hora: {ahora}"

def ejemplo_funcionalidad_1(datos):
    """
    Funcionalidad de ejemplo: valida estructura mínima de 'datos' y devuelve resumen.
    """
    if not isinstance(datos, dict):
        raise ValueError("Se esperaba un diccionario con la estructura del paciente.")
    resumen = {
        "nombre": datos.get("nombre", "N/A"),
        "id": datos.get("id", "N/A"),
        "tareas_pendientes": len(datos.get("tareas", []))
    }
    return resumen

if __name__ == "__main__":
    print(saludo_inicial("<<Mosiah Torres>>"))
    ejemplo = {
        "nombre": "Paciente Ejemplo",
        "id": "P001",
        "tareas": ["Registro", "Asignar cita"]
    }
    print("Resumen ejemplo:", ejemplo_funcionalidad_1(ejemplo))
flowchart TD
  A[Inicio] --> B{¿Paciente registrado?}
  B -- Sí --> C[Mostrar historial]
  B -- No --> D[Registrar paciente]
  D --> C
  C --> E{¿Agendar cita?}
  E -- Sí --> F[Seleccionar servicio]
  F --> G[Confirmar cita]
  E -- No --> H[Fin]
  G --> H
Avance de codificación - Entrega parcial

1) Archivos incluidos:
   - src/main.py (prototipo con saludo y función de ejemplo)
   - docs/diagramas/flujo_funcionalidad_1.mmd (diagrama en Mermaid)
   - requirements.txt
   - README.md

2) Estado:
   - Diseño de la funcionalidad principal en diagrama.
   - Código básico listo para ampliarse.
   - Ambiente: Python 3.8+ sugerido.

3) Pendiente:
   - Implementar módulos de autenticación y base de datos (SQLite/PostgreSQL).
   - Documentar VLSM / VLANs en la carpeta docs/.
   - Subir configuración de Packet Tracer (archivo .pkt) en próximas entregas.

Profesor: este repositorio contiene el primer avance solicitado. Quedo atento a comentarios.
