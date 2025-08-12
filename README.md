# Mosiah_MT
recoup-proyecto/                ← nombre del repo (ej: recoup-proyecto)
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
**Asignatura:** <<Arquitectura de Computadoras y Sistemas Operativos / Introducción a Redes / según corresponda>>  
**Fecha del avance:** <<DD MMMM YYYY>>

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
