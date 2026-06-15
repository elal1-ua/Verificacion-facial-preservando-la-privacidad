#  Verificación Facial Preservando la Privacidad (Synth2Real)

Este repositorio contiene el código, los experimentos y la demostración interactiva del Trabajo de Fin de Grado (TFG) en Ingeniería Informática desarrollado en la **Universidad de Alicante** por **Enrique López Aroca**[cite: 2].

El proyecto aborda el reto de construir sistemas de reconocimiento facial utilizando exclusivamente **datos sintéticos**. Este enfoque preserva la privacidad del usuario y mitiga sesgos demográficos, enfrentándose al desafío técnico de la brecha de dominio (*Domain Gap*) al trasladar el modelo a entornos reales[cite: 2].

---

##  Características Principales

*   **Entrenamiento 100% Sintético:** Uso de los conjuntos de datos *DigiFace* (renderizado 3D) e *IDiffFace-U* (IA generativa/difusión) para el entrenamiento[cite: 2].
*   **Adaptación Eficiente (PEFT):** Implementación de **LoRA** (*Low-Rank Adaptation*) para afinar modelos masivos congelando su conocimiento previo y entrenando solo un **~1%** de los parámetros[cite: 2].
*   **Modelos Fundacionales:** Evaluación comparativa del rendimiento *Zero-Shot* y adaptado de arquitecturas basadas en autoatención: **CLIP ViT-L/14** y **DINOv2 ViT-L/14**[cite: 2].
*   **Interpretabilidad (XAI):** Generación de mapas de activación visual **Grad-CAM** y análisis del espacio latente mediante **PCA** para explicar la toma de decisiones del modelo[cite: 2].

---

##  Demo Interactiva con Streamlit

El proyecto incluye una aplicación web interactiva desarrollada con **Streamlit** para probar el rendimiento de los modelos en tiempo real.

### ¿Qué permite la demo?
1.  **Cargar imágenes:** Sube dos fotografías faciales desde tu equipo.
2.  **Selección de Modelo:** Alterna entre las distintas arquitecturas (CLIP Base, CLIP + LoRA, DINOv2, ResNet-50) para comparar su comportamiento.
3.  **Verificación 1:1:** Calcula al instante la similitud coseno entre los *embeddings* extraídos e indica si pertenecen a la misma identidad basándose en el umbral óptimo calculado.
4.  **Explicabilidad en vivo:** Genera mapas de calor (Grad-CAM) sobre las imágenes subidas para auditar visualmente en qué áreas anatómicas se está centrando la red neuronal.

---

## ⚙️ Instalación y Configuración

Sigue estos pasos para clonar el repositorio y ejecutar tanto los entrenamientos como la demo localmente.

### 1. Clonar el repositorio
```bash
git clone [https://github.com/TU_USUARIO/verificacion-facial-synth2real.git](https://github.com/TU_USUARIO/verificacion-facial-synth2real.git)
cd verificacion-facial-synth2real
