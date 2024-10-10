# Kaggle CV Best11

Это мои решения для 11 соревнований по компьютерному зрению на Kaggle, согласно [списку](https://www.kaggle.com/discussions/general/205017).

## Для каждого соревнования два ноутбука:
1. `base_from_scratch`: базовое решение, реализованное с нуля.
2. `advanced_with_libs`: продвинутое решение, использующее различные библиотеки.

## Используемые инструменты

- **DVC** для версионирования моделей и данных
- **Poetry** для управления зависимостями
- **Pre-commit hooks** для автоматической проверки и форматирования кода
- **GitHub Actions** для CI/CD (настроены прекоммиты)

## Установка и настройка окружения

1. Установите Poetry и все зависимости:
```bash
curl -sSL https://install.python-poetry.org | python3 -
git clone https://github.com/alexmak123/kaggle-CV-best11.git
cd kaggle-CV-best11
poetry install
poetry shell
```
2. Скачайте все данные и модели с диска при помощи DVC:
```bash
dvc init
dvc pull
```

## Соревнования

### 1. Dogs vs. Cats Redux: Kernels Edition

- Ссылка: https://www.kaggle.com/competitions/dogs-vs-cats-redux-kernels-edition
- Метрика качества: Log Loss (меньше значение - лучше результат)

#### Результаты
- `base_from_scratch` (Fully Connected): 0.63
- `base_from_scratch` (Fully Convolutional): 0.60
- `advanced_with_libs` (PyTorch Lightning, TensorBoard + Optuna, Albumentations, timm, captum, ONNX): 0.17

### 2. Flower Classification With Tpus

- Ссылка: https://www.kaggle.com/competitions/flower-classification-with-tpus
- Метрика качества: f1-score (выше значение - лучше результат)

#### Результаты
- `base_from_scratch` (Fully Convolutional): 0.45
- `advanced_with_libs` (Torch XLA, TFRecord Dataset, PyTorch Lightning, Wandb, Albumentations, timm, GradCAM, ONNX): 0.75
