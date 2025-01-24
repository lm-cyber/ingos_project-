# README: Synthetic Data Generator and Fine-Tuning CRAFT with SegFormer

## Проект: Генератор синтетических данных и дообучение CRAFT с SegFormer

### Описание проекта
В рамках этого учебного проекта студенты создадут генератор синтетических данных для задачи детекции текста на изображениях, используя модель **CRAFT (Character-Region Awareness For Text Detection)**. Затем, на основе созданных данных, будет выполнено fine-tuning модели CRAFT с использованием **SegFormer** в качестве её бэкбона.
### Вопросы в телегу 
Алан [Телега](https://t.me/Alan_Nasibullin)
### Цели проекта
1. Разработать генератор синтетических данных, который будет создавать аннотированные изображения для обучения.
2. Использовать созданные данные для дообучения модели CRAFT с SegFormer в качестве бэкбона.
3. Провести анализ качества дообученной модели на тестовых данных.


### TODO преписать запуск
### Как запустить проект
1. Установите зависимости:
   ```bash
   pip install -r requirements.txt
   ```
2. Запустите генерацию синтетических данных:
   ```bash
   python generator/generator.py
   ```
3. Выполните обучение модели:
   ```bash
   python models/train.py
   ```
4. Проверьте результаты модели на тестовых данных:
   ```bash
   python models/evaluate.py
   ```

### Метрики качества
- **IoU (Intersection over Union)** для оценки качества детекции регионов.
- **F1-Score** для текстовых регионов (на основе Precision и Recall).

### Ресурсы и полезные ссылки
- Оригинальная статья CRAFT: [CRAFT Paper](https://arxiv.org/abs/1904.01941)
- Описание SegFormer: [SegFormer Paper](https://arxiv.org/abs/2105.15203)
- репозиторий с имплементацией CRAFT: [CRAFT implementation](https://github.com/clovaai/CRAFT-pytorch)
- Fine-Tune SegFormer от huggingface: [SegFormer Fine-Tune](https://huggingface.co/blog/fine-tune-segformer)
- Открытые датасеты для задач детекции текста:
  - SynthText ([GitHub](https://github.com/ankush-me/SynthText))
  - ICDAR ([ICDAR Website](https://rrc.cvc.uab.es/))
### умные мысли от gpt4o 
### Советы и рекомендации
- Тщательно тестируйте генератор данных, чтобы обеспечить разнообразие и реалистичность.
- Экспериментируйте с параметрами модели, чтобы добиться лучшей производительности.
- Документируйте каждый этап работы для упрощения анализа и воспроизведения результатов.

