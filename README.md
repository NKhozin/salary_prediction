# Предсказание зарплаты по резюме
### Цель проекта

### Датасет
663 547 записей
### Описание файлов репозитория
- baseline.ipynb - 
- experiments.ipynb -
- parser.ipynb -
- predict.ipynb - 
- tg_bot.ipynb -
### Метрики <br />
В качестве основной метрики используется MAPE - cредняя абсолютная ошибка в процентах. Также отслеживаем MAE - средняя абсолютная ошибка.
Значения посчитаны как среднее на 5 фолдах кросс-валидации.
### Эксперименты
| Стадия | Название | MAE | MAPE |
|-------|-------|-------|-------|
| baseline | FastText + LR | 16283.3 | 29.53 |
| baseline | FastText + RidgeRegression | 16267.7 | 29.49 |
| baseline | FastText + LassoRegression | 16266.6 | 29.53 |
| baseline | FastText + KNNRegression | 14986.2 | 27.6 |
| baseline | FastText + DecisionTreeRegressor | 15059.2 | 28.39 |
| baseline | FastText + CatBoostRegressor | **12754.2** | **23.52** |
| exp. 1 | NLTK + FastText + CatBoostRegressor | 12615.5 | 23.24 |
| exp. 1 | Spacy + FastText + CatBoostRegressor | **12580.7** | **23.17** |
| exp. 1 | StemLemPipe + FastText + CatBoostRegressor | 12616.2 | 23.25 |
| exp. 2 |  CatBoostRegressor with text_features v.1 | 13267 | 24.56 |
| exp. 2 |  Spacy + CatBoostRegressor with text_features v.1 | 13274.3 | 24.56 |
| exp. 2 |  Spacy + CatBoostRegressor with text_features v.2 | 13823.3 | 25.45 |
| exp. 2 |  FastText + CatBoostRegressor with text_features v.1 | 13137.9 | 24.25 |
| exp. 2 |  FastText + CatBoostRegressor with text_features v.2 | 14043 | 25.73 |
| exp. 3 | multilingual_e5+CatBoostRegressor | 13564.8 | 20.4 |
| hyperparameter tuning | FastText+CatBoostRegressor | **10936** | **20.4** |

### SHAP
![image](https://github.com/NKhozin/salary_prediction/assets/92330362/a9ee1d9c-c3bd-404b-b40f-21a39f7480e4)
![image](https://github.com/NKhozin/salary_prediction/assets/92330362/3e572c7c-3f3c-4ab0-b5cb-91671f5d8fb8)

### Выводы
В результате проделанных экспериментов значение целевой метрики упало на ~3% относительно бейзлайна. Однако в выборке для обучения большое число повторяющихся профессий, а имеющиеся смещены в сторону "рабочих".
### Дальнейшие планы
- расширение выборки
- эксперименты с применением новых NLP подходов - 
