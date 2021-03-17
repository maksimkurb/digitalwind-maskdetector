# Распознавание наличия медицинской маски на лице человека

## Описание
Данная модель позволяет предсказать наличие или
отсутствие медицинской маски на лице человека

## Демо на Google Colab
[Google Colab](https://colab.research.google.com/drive/1fLp45pnSCRIBeCcBOepuqfU3XxTldRD3?usp=sharing)

## Запуск
1. Убедитесь, что установлен Python версии 3.7 или 3.8:
```bash
> python --version
Python 3.8.8
```

2. Установите зависимости в виртуальном окружении
```bash
pip install virtualenv
virtualenv venv

source venv/bin/activate # для Linux
CALL venv/Scripts/activate # для Windows

pip install -r requirements.txt
```

3. Запустите детектор маски на изображении
```bash
python detect_mask_on_image.py --image dataset/test/mask/701.png
```

4. (Оционально) Запустите детектор маски на потоковом видео
```bash
# Для запуска детектора маски на потоковом видео требуется
# наличие веб-камеры на устройстве
python detect_mask_on_video.py
```

## Обучение модели
Датасет находится в папке `dataset/train` и включает в себя:
* 2681 изображение лиц без маски
* 700 изображений лиц с маской

Для запуска обучения модели нужно запустить следующий скрипт в venv:
```
python train_model.py
```

Для тестирования модели можно использовать изображения из папки `dataset/test`.
Эти изображения не были использованы при обучении модели.