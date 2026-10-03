# Car Price Prediction

Проект по анализу данных и прогнозированию стоимости автомобилей с использованием алгоритмов машинного обучения.

## О проекте

В работе проведён анализ датасета объявлений о продаже автомобилей и построена модель для прогнозирования их стоимости.

**Размер датасета:** 8120 записей, 16 признаков.

### Основные признаки

* тип кузова;
* коробка передач;
* год регистрации;
* мощность;
* модель и марка автомобиля;
* пробег;
* тип топлива;
* наличие ремонта;
* цена.

## Что сделано

* проведён первичный анализ и исследовательский анализ данных (EDA);
* обработаны пропуски и выбросы;
* выполнена подготовка числовых и категориальных признаков;
* разработан собственный трансформер для предобработки данных;
* использован `Pipeline` для объединения этапов обработки и обучения;
* обучено и сравнено несколько моделей;
* выполнен подбор гиперпараметров с помощью `GridSearchCV`;
* рассчитана permutation importance для оценки влияния признаков;
* использован базовый `DummyRegressor` для сравнения качества моделей.

## Использованные модели

* Decision Tree;
* Random Forest;
* XGBoost;
* LightGBM;
* CatBoost;
* Dummy Regressor.

## Результаты

Лучший результат показала модель **CatBoost**.

| Модель          |     RMSE |
| --------------- | -------: |
| Dummy Regressor | 10 637 € |
| CatBoost        |  5 347 € |

Модель CatBoost снизила RMSE примерно в 2 раза относительно базовой модели.

Наиболее значимыми признаками по permutation importance оказались:

* `VehicleType`;
* `RegistrationYear`;
* `Repaired`.

## Стек

**Python:**
Pandas, NumPy, Scikit-learn, CatBoost, LightGBM, XGBoost

**Визуализация:**
Matplotlib, Seaborn

**Среда:**
Jupyter Notebook

## Структура проекта

```text
car-price-prediction/
├── car_price_prediction.ipynb
├── cars_price.csv
├── .gitignore
└── README.md
```

## Запуск

Клонировать репозиторий:

```bash
git clone https://github.com/margoshka-dema/car-price-prediction.git
cd car-price-prediction
```

Установить необходимые библиотеки:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn catboost lightgbm xgboost
```

Открыть `car_price_prediction.ipynb` в Jupyter Notebook или JupyterLab и выполнить ячейки последовательно.
