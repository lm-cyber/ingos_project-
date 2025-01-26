# Генератор синтетических данных и дообучение SegFormer для работы с CRAFT

## Описание проекта

В рамках этого учебного проекта студенты разработают генератор синтетических данных для задачи детекции текста на изображениях, используя подход CRAFT (Character-Region Awareness For Text Detection). На основе сгенерированных данных будет выполнено fine-tuning модели SegFormer для улучшения работы в рамках алгоритма CRAFT.

Проект состоит из следующих этапов:
1. Улучшение генератора синтетических данных.
2. Дообучение SegFormer на основе созданных данных.
3. Настройка гиперпараметров для CRAFT.

---

## Этап 1: Улучшение генератора синтетических данных

### Задачи
- **Добавление новых шрифтов и фонов:** Обеспечить разнообразие данных, добавив больше шрифтов и текстур для фоновых изображений.
- **Оптимизация производительности:** Реализовать возможность параллельной генерации данных для сокращения времени выполнения.
- **Добавление аугментаций:**
  - Для текста и фона отдельно (например, изменение размеров, перспективы, добавление шумов).
  - Аугментации, изменяющие размер и перспективу, должны применяться как к изображению, так и к соответствующим маскам.
  - Аугментации, изменяющие цвета или добавляющие артефакты, должны применяться только к изображениям, не затрагивая маски.
- **Работа с параметрами генерации маски:** Настроить параметры для более точного отображения текстовых областей.

---

## Этап 2: Дообучение SegFormer

### Что нужно сделать
- **Подобрать правильный loss:** определить подходящую функцию потерь для задачи детекции текста.
- **Настроить гиперпараметры:** выбрать оптимальные значения параметров обучения (например, скорость обучения, размер батча).
- **Добавить метрики для валидации:**
  - Вычисление IoU (Intersection over Union) и F1-Score.
  - Так как метрики для маски не целевые, нужно преобразовать результаты работы модели в bounding boxes и использовать их для расчета метрик.
- **Не валидироваться на синтетических данных:** необходимо проводить валидацию только на реальных данных для получения объективной оценки качества модели.
---

## Этап 3: Настройка гиперпараметров для CRAFT

Для настройки гиперпараметров алгоритма CRAFT использовать библиотеку **Optuna**. Оптимизация должна быть основана на метриках IoU и F1-Score.

---

## Структура репозитория

- `example_eval.ipynb` — пример валидации предсказаний SegFormer.
- `example_segformer_train.ipynb` — пример обучения SegFormer.
- `gen_synt_data_example.ipynb` — пример генерации синтетических данных.

---

## Метрики качества

Для оценки качества работы использовать следующие метрики:
1. **IoU (Intersection over Union):**
   - Для оценки перекрытия предсказанной и истинной масок.
2. **F1-Score:**
   - Для оценки качества детекции текстовых областей.

---

## Полезные ресурсы

### Ресурсы и полезные ссылки
- Оригинальная статья CRAFT: [CRAFT Paper](https://arxiv.org/abs/1904.01941)
- Описание SegFormer: [SegFormer Paper](https://arxiv.org/abs/2105.15203)
- репозиторий с имплементацией CRAFT: [CRAFT implementation](https://github.com/clovaai/CRAFT-pytorch)
- Fine-Tune SegFormer от huggingface: [SegFormer Fine-Tune](https://huggingface.co/blog/fine-tune-segformer)
- Открытые датасеты для задач детекции текста:
 
### Датасеты для валидации (Не валидироваться на синтетических данных)
- SynthText ([GitHub](https://github.com/ankush-me/SynthText))
- ICDAR ([ICDAR Website](https://rrc.cvc.uab.es/))

---
### Вопросы в телегу 
Алан [Телега](https://t.me/Alan_Nasibullin)

## Планируемые результаты

К завершению проекта студенты:
1. Создадут производительный генератор синтетических данных
2. Реализуют эффективное дообучение модели SegFormer для улучшения детекции текста.
3. Настроят CRAFT для достижения наилучших метрик IoU и F1-Score.

