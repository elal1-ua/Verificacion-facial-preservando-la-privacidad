---
title: TFG Biometría
colorFrom: blue
colorTo: indigo
sdk: docker
app_port: 8501
tags:
- streamlit
- biometrics
- deep-learning
- computer-vision
- lora
pinned: false
short_description: Demo interactiva para ver el mapa de calor con grad-cam
---

# Reconocimiento Biométrico y Brecha de Dominio (Demo)

 **Acceso a la aplicación a pantalla completa:** [https://enrique2023-tfg-biometria-gradcam.hf.space](https://enrique2023-tfg-biometria-gradcam.hf.space)

Esta aplicación web es una demostración interactiva desarrollada como complemento práctico al Trabajo de Fin de Grado del doble grado en Ingeniería Informática y ADE de la Universidad de Alicante.

##  ¿Qué hace esta aplicación?
Esta interfaz ha sido diseñada para tangibilizar los resultados de la investigación. Permite calcular y visualizar la similitud entre imágenes biométricas, sirviendo como prueba empírica para observar cómo se comportan los modelos fundacionales frente al cambio de dominio (escenarios *Synth2Real*, pasando de datos sintéticos a reales).

##  Tecnologías y Modelos
* **Frontend:** Construido con [Streamlit](https://streamlit.io/) para una interacción fluida y en tiempo real.
* **Modelos Subyacentes:** Arquitecturas basadas en atención (*Vision Transformers*, CLIP), evaluando el impacto del ajuste paramétrico eficiente (LoRA) para superar el *domain gap*.
* **Despliegue:** Contenerizado mediante Docker para asegurar su reproducibilidad.


---

##  Ejecución en local (Para desarrolladores)

Si deseas inspeccionar el código o ejecutar esta demostración en tu propia máquina:

1. Clona este repositorio.
2. Instala las dependencias necesarias.
3. Ejecuta el servidor local de Streamlit apuntando al script principal:

```bash
streamlit run src/streamlit_app.py