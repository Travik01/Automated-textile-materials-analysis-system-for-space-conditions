# Textile Material Analysis System

Automated textile analysis system for aerospace and aviation industries. Uses a convolutional neural network (CNN) to detect fabric defects from image data.

## Features
- **Defect detection** — CNN-based image classification (5 classes)
- **64×64 image processing** — loads and normalizes patches from dataset
- **Training & evaluation** — train/test split with accuracy metrics
- **Model export** — saves trained model as `.keras`

## Installation
```bash
pip install tensorflow scikit-learn numpy pandas seaborn Pillow
```

## Dataset
Download from Kaggle: [TILDA 400 64x64 Patches](https://www.kaggle.com/datasets/angelolmg/tilda-400-64x64-patches) — unzip into a folder named `AA/` in the project root.

Expected structure:
```
AA/
├── class_1/    # images .png/.jpg
├── class_2/
├── class_3/
├── class_4/
└── class_5/
```

## Usage
```bash
python COD.py
```

The script will:
1. Load images from `AA/` (64×64, normalized to 0–1)
2. Encode labels and split 80/20 into train/test
3. Train a CNN (Conv2D 32 → Conv2D 64 → Dense 128 → Dense 5 softmax)
4. Save the model to `my_model.keras`

## Model Architecture
```
Conv2D(32, 3×3, relu) → MaxPool(2×2)
Conv2D(64, 3×3, relu) → MaxPool(2×2)
Flatten → Dense(128, relu) → Dense(5, softmax)
```
- **Optimizer:** Adam
- **Loss:** categorical_crossentropy
- **Batch size:** 64
- **Epochs:** 3

## Project Structure
```
textile-analysis-system/
├── COD.py            # All code (data loading, training, saving)
├── AA/               # Dataset folder (unzip TILDA here)
├── my_model.keras     # Trained model (generated after run)
└── README.md
```

## Requirements
Python ≥ 3.8, TensorFlow, scikit-learn, NumPy, Pandas, Seaborn, Pillow

## License
MIT

---

# Система анализа текстильных материалов

Автоматизированная система анализа тканей для авиационной и космической промышленности. Использует свёрточную нейросеть (CNN) для обнаружения дефектов по изображениям.

## Возможности
- **Обнаружение дефектов** — классификация изображений на 5 классов с помощью CNN
- **Обработка 64×64** — загрузка и нормализация патчей из датасета
- **Обучение и оценка** — разделение на train/test с метрикой accuracy
- **Экспорт модели** — сохранение обученной модели в `.keras`

## Установка
```bash
pip install tensorflow scikit-learn numpy pandas seaborn Pillow
```

## Датасет
Скачать с Kaggle: [TILDA 400 64x64 Patches](https://www.kaggle.com/datasets/angelolmg/tilda-400-64x64-patches) — распаковать в папку `AA/` в корне проекта.

Ожидаемая структура:
```
AA/
├── class_1/    # изображения .png/.jpg
├── class_2/
├── class_3/
├── class_4/
└── class_5/
```

## Использование
```bash
python COD.py
```

Скрипт:
1. Загружает изображения из `AA/` (64×64, нормализация 0–1)
2. Кодирует метки и делит 80/20 на train/test
3. Обучает CNN (Conv2D 32 → Conv2D 64 → Dense 128 → Dense 5 softmax)
4. Сохраняет модель в `my_model.keras`

## Архитектура модели
```
Conv2D(32, 3×3, relu) → MaxPool(2×2)
Conv2D(64, 3×3, relu) → MaxPool(2×2)
Flatten → Dense(128, relu) → Dense(5, softmax)
```
- **Оптимизатор:** Adam
- **Функция потерь:** categorical_crossentropy
- **Размер батча:** 64
- **Эпохи:** 3

## Структура проекта
```
textile-analysis-system/
├── COD.py            # Весь код (загрузка данных, обучение, сохранение)
├── AA/               # Папка с датасетом (распаковать TILDA сюда)
├── my_model.keras     # Обученная модель (создаётся после запуска)
└── README.md
```

## Зависимости
Python ≥ 3.8, TensorFlow, scikit-learn, NumPy, Pandas, Seaborn, Pillow


