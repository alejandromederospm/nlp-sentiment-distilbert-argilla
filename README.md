# NLP Sentiment Analysis with DistilBERT + Argilla

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?logo=python&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-Transformers-FFD21E?logo=huggingface&logoColor=black)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?logo=pytorch&logoColor=white)
![Argilla](https://img.shields.io/badge/Argilla-Data--Centric%20AI-00B4D8)
![License](https://img.shields.io/badge/License-MIT-green)

Sentiment analysis pipeline on the **Banking77** dataset using **DistilBERT** fine-tuning with the HuggingFace Transformers Trainer API, combined with **Argilla** for data annotation and labeling workflows. The project implements an **active learning loop** that iterates through pretrained inference, human labeling, fine-tuning, and re-labeling to continuously improve model performance with a data-centric approach.

## Pipeline

```
+---------------------+       +---------------------+       +---------------------+
|  1. Pretrained       |       |  2. Argilla          |       |  3. Fine-Tune        |
|     DistilBERT       | ----> |     Annotation       | ----> |     with Trainer     |
|     Inference        |       |     & Labeling       |       |     API              |
+---------------------+       +---------------------+       +---------------------+
         ^                                                            |
         |                                                            |
         +------------------------------------------------------------+
                          Active Learning Loop
                     (Re-label with improved model)
```

## Key Features

- **Transfer Learning**: Fine-tuning DistilBERT on domain-specific banking customer intent data (Banking77 dataset with 77 intent categories).
- **Data-Centric AI with Argilla**: Interactive annotation and labeling interface for reviewing, correcting, and enriching training data.
- **Active Learning Pipeline**: Iterative cycle of prediction, human review, retraining, and re-prediction to maximize label quality with minimal annotation effort.
- **HuggingFace Trainer API**: Streamlined training loop with built-in evaluation, logging, and checkpoint management.
- **Comprehensive Evaluation**: Classification metrics including accuracy, precision, recall, and F1-score across all intent categories.

## Tech Stack

| Component         | Technology                          |
|-------------------|-------------------------------------|
| Base Model        | DistilBERT (HuggingFace)            |
| Training          | Transformers Trainer API            |
| Annotation        | Argilla                             |
| Dataset           | Banking77 (HuggingFace Datasets)    |
| Deep Learning     | PyTorch                             |
| Acceleration      | HuggingFace Accelerate              |
| Visualization     | Matplotlib, Seaborn                 |

## How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/nlp-sentiment-distilbert-argilla.git
   cd nlp-sentiment-distilbert-argilla
   ```

2. **Create a virtual environment and install dependencies**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. **Start Argilla server** (required for annotation workflow)
   ```bash
   argilla server start
   ```

4. **Run the notebooks** in order:
   - `01_eda_and_baseline.ipynb` - Exploratory analysis and pretrained model inference
   - `02_argilla_annotation.ipynb` - Data annotation and labeling with Argilla
   - `03_fine_tuning.ipynb` - Fine-tune DistilBERT with Trainer API
   - `04_active_learning.ipynb` - Active learning loop and re-labeling

## Project Structure

```
nlp-sentiment-distilbert-argilla/
├── notebooks/          # Jupyter notebooks for each pipeline stage
├── src/                # Source code and utilities
├── data/               # Dataset files and annotations
├── models/             # Saved model checkpoints
├── requirements.txt
├── .gitignore
└── README.md
```

---

# NLP Analisis de Sentimiento con DistilBERT + Argilla (ES)

Pipeline de analisis de sentimiento sobre el dataset **Banking77** utilizando fine-tuning de **DistilBERT** con la API Trainer de HuggingFace Transformers, combinado con **Argilla** para flujos de trabajo de anotacion y etiquetado de datos. El proyecto implementa un **ciclo de aprendizaje activo** que itera entre inferencia del modelo preentrenado, etiquetado humano, fine-tuning y re-etiquetado para mejorar continuamente el rendimiento del modelo con un enfoque centrado en los datos.

## Pipeline

```
+---------------------+       +---------------------+       +---------------------+
|  1. DistilBERT       |       |  2. Anotacion        |       |  3. Fine-Tuning      |
|     Preentrenado     | ----> |     con Argilla       | ----> |     con Trainer      |
|     Inferencia       |       |     & Etiquetado      |       |     API              |
+---------------------+       +---------------------+       +---------------------+
         ^                                                            |
         |                                                            |
         +------------------------------------------------------------+
                     Ciclo de Aprendizaje Activo
                  (Re-etiquetar con modelo mejorado)
```

## Caracteristicas Principales

- **Transferencia de Aprendizaje**: Fine-tuning de DistilBERT sobre datos de intencion de clientes bancarios (Banking77 con 77 categorias).
- **IA Centrada en Datos con Argilla**: Interfaz interactiva de anotacion y etiquetado para revisar, corregir y enriquecer datos de entrenamiento.
- **Pipeline de Aprendizaje Activo**: Ciclo iterativo de prediccion, revision humana, reentrenamiento y re-prediccion.
- **API Trainer de HuggingFace**: Bucle de entrenamiento simplificado con evaluacion, logging y gestion de checkpoints integrados.
- **Evaluacion Integral**: Metricas de clasificacion incluyendo accuracy, precision, recall y F1-score.

## Como Ejecutar

1. **Clonar el repositorio**
   ```bash
   git clone https://github.com/<tu-usuario>/nlp-sentiment-distilbert-argilla.git
   cd nlp-sentiment-distilbert-argilla
   ```

2. **Crear entorno virtual e instalar dependencias**
   ```bash
   python -m venv venv
   source venv/bin/activate  # En Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. **Iniciar servidor Argilla** (necesario para el flujo de anotacion)
   ```bash
   argilla server start
   ```

4. **Ejecutar los notebooks** en orden:
   - `01_eda_and_baseline.ipynb` - Analisis exploratorio e inferencia del modelo preentrenado
   - `02_argilla_annotation.ipynb` - Anotacion y etiquetado de datos con Argilla
   - `03_fine_tuning.ipynb` - Fine-tuning de DistilBERT con Trainer API
   - `04_active_learning.ipynb` - Ciclo de aprendizaje activo y re-etiquetado
