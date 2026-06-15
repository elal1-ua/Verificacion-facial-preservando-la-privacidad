````md
#  Verificación Facial Preservando la Privacidad (Synth2Real)

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Spaces-F59E0B?logo=huggingface&logoColor=white)
![Deep Learning](https://img.shields.io/badge/Deep%20Learning-PyTorch-EE4C2C?logo=pytorch&logoColor=white)

Repositorio oficial del Trabajo de Fin de Grado (TFG) en Ingeniería Informática desarrollado en la **Universidad de Alicante (UA)** por **Enrique López**.

Este proyecto aborda el reto de construir sistemas de reconocimiento facial robustos utilizando exclusivamente **datos sintéticos**. Este enfoque preserva la privacidad del usuario, evita problemas legales de protección de datos y mitiga sesgos demográficos. El principal desafío técnico resuelto es la superación de la brecha de dominio (*Domain Gap*) al trasladar modelos entrenados en entornos virtuales a escenarios del mundo real.

---

##  Demo Interactiva en Vivo

El proyecto incluye una aplicación web interactiva desplegada en la nube para probar el rendimiento de los modelos en tiempo real.

 **[Acceder a la Demo Interactiva (Streamlit)](https://enrique2023-tfg-biometria-gradcam.hf.space)**

### ¿Qué permite la demo?

1. **Verificación 1:1:** Sube dos fotografías faciales y el sistema calculará al instante la similitud coseno entre sus *embeddings*, determinando si pertenecen a la misma identidad.
2. **Selección de Arquitecturas:** Alterna en vivo entre modelos tradicionales (ResNet-50) y modelos fundacionales ajustados (CLIP ViT-L/14, DINOv2 ViT-L/14).
3. **Explicabilidad (XAI):** Genera mapas de calor **Grad-CAM** directamente sobre las imágenes subidas para auditar visualmente en qué áreas anatómicas se está centrando la red neuronal para tomar su decisión.

---

##  Características Principales de la Investigación

- **Entrenamiento 100% Sintético:** Uso de los conjuntos de datos *DigiFace* (renderizado 3D) e *IDiffFace-U* (IA generativa por difusión) para entrenar los modelos desde cero en la tarea biométrica.
- **Adaptación Eficiente (PEFT):** Implementación de **LoRA** (*Low-Rank Adaptation*) para afinar modelos masivos, congelando su conocimiento previo y entrenando solo un **~1%** de los parámetros.
- **Modelos Fundacionales:** Evaluación comparativa del rendimiento *Zero-Shot* frente a los modelos adaptados con atención global (CLIP y DINOv2).
- **Prevención del Sobreajuste:** Estrategia de *Early Stopping* basada en el *gap* de similitud sobre un conjunto de datos real (CASIA-WebFace) para evitar la memorización del simulador.

---

##  Instalación y Configuración Local

Si deseas ejecutar el código, los entrenamientos o la demo en tu propia máquina, sigue estos pasos:

### 1. Clonar el repositorio

```bash
git clone https://github.com/TU_USUARIO/verificacion-facial-synth2real.git
cd verificacion-facial-synth2real
````

### 2. Crear un entorno virtual (Recomendado)

```bash
python -m venv venv

# Linux / macOS
source venv/bin/activate

# Windows
venv\Scripts\activate
```

### 3. Instalar las dependencias

```bash
pip install -r requirements.txt
```

### 4. Ejecutar la aplicación Streamlit en local

```bash
streamlit run app.py
```

---

##  Resultados Destacados

El ajuste fino mediante LoRA demostró ser la estrategia más robusta para mitigar la brecha de dominio. Al evaluar en el conjunto de datos del mundo real (*CASIA-WebFace*), se obtuvieron los siguientes resultados en la Tasa de Igual Error (**EER**):

| Modelo             | EER (%)    | Observaciones                                 |
| ------------------ | ---------- | --------------------------------------------- |
| ResNet-50 (FFT)    | 36.90%     | Colapso por sobreajuste a texturas sintéticas |
| DINOv2 + LoRA      | 29.55%     | Atención difusa y ruido en el fondo           |
| **CLIP + LoRA**  | **14.75%** | Mejor rendimiento general                     |

### Interpretabilidad mediante Grad-CAM

El análisis visual mostró que:

* **ResNet-50** tendía a centrarse en artefactos y texturas sintéticas.
* **DINOv2 + LoRA** distribuía la atención de forma excesivamente amplia.
* **CLIP + LoRA** focalizaba consistentemente regiones estructurales relevantes del rostro (ojos, nariz y contorno facial), mejorando la generalización al dominio real.

---

##  Tecnologías Utilizadas

* Python 3.10+
* PyTorch
* Transformers (Hugging Face)
* PEFT (LoRA)
* OpenCV
* NumPy
* Scikit-Learn
* Streamlit
* Grad-CAM
* CLIP ViT-L/14
* DINOv2 ViT-L/14
* ResNet-50

---


##  Autor

**Enrique López**

Trabajo de Fin de Grado (TFG)
Grado en Ingeniería Informática

---

##  Agradecimientos

A la Universidad de Alicante, a los directores del trabajo y a la comunidad científica de visión por computador por el desarrollo de modelos fundacionales abiertos que han hecho posible esta investigación.

---

⭐ Si este proyecto te resulta útil, considera darle una estrella al repositorio.

```
```
