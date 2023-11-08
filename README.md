# Улучшение яркости изображения
## Описание задачи
* Задача - улучшение яркости изображения
* Язык программирования Python
* Ограничений по использованию библиотек и сторонних функций нет

## Датасет
Набор данных содержит содержит 745 примеров тёмных картинок. В каталоге low хранятся тёмные изображения, в каталоге high - соответсвующие им яркие изображения. Пример загрузки датасета в PyTorch приведён в файле dataset.py       
[Ссылка на датасет](https://drive.google.com/file/d/1ThoPb1flnfXDpRIytgBd7_e9Kv_lPnbo/view) 

## Метрики
Пример расчёта метрик представлен в файле evaluation.py. Для оценки качества используются следующие метрики:
* [PSNR](https://ru.wikipedia.org/wiki/Пиковое_отношение_сигнала_к_шуму) - Пиковое отношение сигнала к шуму;
* [SSIM](https://ru.wikipedia.org/wiki/SSIM) - Индекс структурного сходства;
* [LPIPS](https://github.com/richzhang/PerceptualSimilarity#c-about-the-metric) - Learned Perceptual Image Patch Similarity.  

## Выбранная модель
* Выбранная модель - Zero DCE. основанная на Cверточных слоях и оптимизации кривых при помощи 4х loss-ов.
* batch_size = 16, 200 эпох, обучение с помощью оптимизатора Adam
* Для обучения модели не требуются светлые изображения

[Ссылка на решение в Google Colab](https://colab.research.google.com/drive/1TW0hTOlcpjV2A0rYrGRcqyb04dckylfr?usp=sharing)


![Модель Zero-DCE](https://github.com/VladislavEpifanow/cv_lab4/blob/main/results-example/ZERO-DCE.png)


## Результаты:
Пример работы на изображении:
* Тёмное изображение:
  
![low_light_img](https://github.com/VladislavEpifanow/cv_lab4/blob/main/results-example/low_img.png)
* Результат модели:
  
![model_img](https://github.com/VladislavEpifanow/cv_lab4/blob/main/results-example/Model_img.png)
* Реальное светлое изображение:
  
![model_img](https://github.com/VladislavEpifanow/cv_lab4/blob/main/results-example/Real_high_img.png)

* Полученные метрики:
  
|PSNR|SSIM|LPIPS|
|:---:|:---:|:---:
15.83|0.61|0.23
