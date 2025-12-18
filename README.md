# boTeach – Tutor Virtual Educativo basado en IA

## Trabajo Final de Grado – Ingeniería Informática  
**Presentado y defendido el lunes 15 de diciembre del año 2025**  
**Calificación final: 10 (diez)**

---

## Introducción

**boTeach** es un chatbot educativo que desarrollé como **Trabajo Final de Grado** de la carrera de Ingeniería Informática. El proyecto consiste en un **tutor virtual inteligente** capaz de acompañar a los estudiantes durante su proceso de estudio **utilizando exclusivamente sus propios apuntes en PDF**.

A diferencia de los chatbots tradicionales, boTeach **no entrega respuestas directas**. Su enfoque pedagógico está inspirado en el rol de un docente: 

**Enseñar a pensar**, guiando al estudiante mediante pistas, fomentando la reflexión y evaluando su comprensión real del contenido.

---

## Problema que aborda

La educación virtual y el estudio autónomo presentan desafíos persistentes:

- Menor interacción docente–estudiante  
- Tiempos de respuesta lentos  
- Dificultad para estudiar únicamente con PDFs  
- Falta de retroalimentación personalizada  

**boTeach** nace para acompañar este proceso, ofreciendo **asistencia inmediata, guiada y contextualizada**, sin reemplazar al docente.

---

## ¿Qué hace diferente a boTeach?

- **Guía en lugar de responder**  
  Genera *pistas* que orientan al estudiante hacia la respuesta correcta.

- **Evalúa la comprensión**  
  Compara la respuesta del alumno con la respuesta oficial usando **similitud semántica (coseno)**.

- **Fidelidad estricta al PDF**  
  Responde **únicamente** con información contenida en el documento cargado.

- **Detecta cuando no puede responder**  
  Evita alucinaciones y lo comunica explícitamente.

- **100% local**  
  Funciona con un modelo ejecutado en **Ollama**, sin depender de la nube.

- **Adaptable a cualquier materia**  
  Solo requiere un PDF como fuente de conocimiento.

---

## Arquitectura y funcionamiento

boTeach implementa una arquitectura basada en **Retrieval-Augmented Generation (RAG)**:

### Preprocesamiento del PDF
- Limpieza del texto  
- División en fragmentos (*chunking*) con **LangChain**  
- Generación de embeddings con **SentenceTransformers**

### Base vectorial
- Almacenamiento de embeddings en **ChromaDB**

### Recuperación
- Búsqueda de los fragmentos más relevantes según la consulta

### Generación
- El modelo **Gemma 7B Instruct** (ejecutado en Ollama) produce:
  - Una **pista**
  - Una **respuesta oficial**

### Evaluación
- Comparación semántica entre:
  - Respuesta del estudiante  
  - Respuesta oficial del sistema

---

## Tecnologías utilizadas

- Python 3.9  
- PyPDF2  
- LangChain  
- SentenceTransformers  
- Torch  
- ChromaDB  
- Ollama  
- Gemma 7B Instruct  
- JSON para estructurar la salida del modelo  

---

## Resultados de la evaluación

El sistema fue evaluado con **50 preguntas** generadas a partir de un PDF educativo y **9 participantes**:

- **Fidelidad al PDF:** 30 respuestas con puntaje máximo  
- **Claridad de las respuestas:** 26 evaluaciones con puntaje máximo  
- **Pertinencia:** 24 evaluaciones con puntaje máximo  
- **Eficacia de las pistas:** mayoría de calificaciones entre 4 y 5  
- **Detección de información no disponible:** correcta en el 100% de los casos diseñados para probarlo  

Estos resultados demuestran que **boTeach puede funcionar como un tutor virtual confiable**, especialmente para estudiantes que trabajan con materiales propios.

---

## Reflexión final

Este proyecto me permitió explorar cómo la **Inteligencia Artificial puede complementar la labor docente**, no reemplazarla. Herramientas como boTeach pueden contribuir a una educación más:

- Personalizada  
- Interactiva  
- Accesible  

El proyecto continuará evolucionando mediante pruebas con nuevos modelos, embeddings y bases vectoriales, así como evaluaciones con estudiantes reales.

---

## Autor

**Lucas Javier Castronuovo**  
Ingeniería Informática  
Trabajo Final de Grado  

