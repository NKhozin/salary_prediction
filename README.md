# Предсказание зарплаты по резюме
### Цель проекта

### Датасет
663 547 записей
### Описание файлов репозитория

### Метрики <br />
В качестве основной метрики используется MAPE - cредняя абсолютная ошибка в процентах. Также отслеживаем MAE - средняя абсолютная ошибка:
### Эксперименты
| Описание | Результат |
|-------|-------|
| Эмбеддинги из различных энкодеров: multilingual-e5-large, rubert-tiny2, MiniLM-L12-v2, DeepPavlov rubert-base-cased-sentence | multilingual-e5-large показала наилучшие результаты по качеству получаемых эмбеддингов - в топ релевантных вакансий семантического поиска попадают результаты с идентичной должностью. Кроме того, есть совпадения по региону и преимущественная близость мэтчей в опыте работы |
| Классификатор для результатов семантического поиска | Pre-trained модели для реранжирования результатов не показали ощутимого прироста качества |
| HRBert-mini| Семантический поиск на эмбеддингах из модели “as is” дает в основном мало релевантные результаты |
| Эмбеддинги FastText с очисткой данных | FastText хуже улавливает семантическую близость между вакансиями и резюме, где содержание не совпадает в точности, но схоже по смыслу |
| Эмбеддинги multilingual-e5-large признаков по отдельности. Например, (эмбединги описания вакансий/резюме + эмбединги остальных признаков) | Результаты отличается незначительно от исходного варианта |