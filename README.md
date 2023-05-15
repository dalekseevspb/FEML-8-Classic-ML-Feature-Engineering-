# FEML-8_(Feature Engineering & Classic Machine Learning: Работа с признаками и построение моделей "классического" машинного обучения)

# (#2) «Классификация: Логистическая регрессия и метод опорных векторов(SVM)»: 
Классификация уровня дохода человека (больше/меньше 50000 долл.) на основании набора признаков

# (#3) «Функции потерь и оптимизация».
- Реализовать логистическую регрессию "с нуля" на датасете "Ирисы Фишера"
- Обучить ее методом градиентного спуска:
  - "Стандартным" способом
  - Методом nesterov momentum
  - Методом rmsprop

# (#4) «Оценка точности модели, переобучение, регуляризация»:
- расчет True Positive Rate, False Positive Rate, Precision, Recall
- график ROC AUC

# (#5) «Проблема качества данных»:
- Cформируем произвольный датасет на 5000 записей, описывающих стоимость поездок на разных автомобилях на дальние расстояния
- оценим изменение качества предсказаний (MAE в модели лин.регрессии) при удалении части признаков
- оценим изменение качества предсказаний (MAE в модели лин.регрессии) при ухудшении качества входящих данных (введём выбросы и пропуски данных в датасет)

# (#6) «Работа с переменными»:
- проведите эксплоративный анализ данных (EDA) на датасете недвижимости Бостона и обучите линейную модель наиболее качественно

# (#7) «Деревья решений»:
- взять датасет недвижимости Бостона
- построить модель линейной регрессии, дерево решений, оптимизировать параметры (поэкспериментировать с параметрами дерева решений) и сравнить результаты
- визуализировать дерево решений штатной библиотекой (tree) и посредством GraphViz

# (#8) "Поиск выбросов и генерация новых признаков":
- Взять датасет https://www.kaggle.com/c/sberbank-russian-housing-market/overview
- Провести EDA с акцентом на пропущенные значения и выбросы
- Обучить простую модель несколько раз (см. ниже) и сравнить качество.
- При обучении модели постепенно фильтровать выбросы и заполнять пропуски. При необходимости обосновывать выбранные методы.
- Сгенерировать не менее новых 5 признаков (генерацию с помощью PolynomialFeatures считать как один признак) и обучить модель после каждого добавления нового признака для контроля качества.
- Построить изменения качества график качества модели на каждом шаге (после обработки каждого признака и после каждого добавления нового признака). 

# (#9) «Feature Selection»:
1) Взять данные по классификации типов лесов в США (the covertype dataset (classification) https://scikit-learn.org/stable/modules/generated/sklearn.datasets.fetch_covtype.html#sklearn.datasets.fetch_covtype)
2) Провести EDA
3) Построить зависимость между качеством модели и количеством отобранных признаков, т.е. надо обучать модель на количестве признаков от одного до максимально возможного. (лог.регрессия,  DecisionTreeClassifier)
4) Для отбора признаков использовать следующие подходы:
- корреляция признаков (на основе матрицы корреляции) и отбор по величине корреляции
- отбор признаков на основе Information Value (см. статью https://medium.com/mlearning-ai/weight-of-evidence-woe-and-information-value-iv-how-to-use-it-in-eda-and-model-building-3b3b98efe0e8)
- отбор признаков на основе feature_importance от алгоритма RandomForest
- жадный отбор признаков по максимальному нарастанию качества модели
- жадное отбрасывание признаков по минимальному падению качества модели

# (#10) «Ансамблирование, стекинг»:
Решаем задачу регрессии - предскажем цены на недвижимость. 
- Использовать датасет https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data  (train.csv)
- Построить случайный лес, вывести важность признаков
- Обучить стекинг как минимум 3х моделей, использовать хотя бы 1 линейную модель и 1 нелинейную

# (#11) Алгоритмы кластеризации и анализ текста:
В предложенных файлах информация с публичных слушаний г.Москвы по правилам землепользования и застройки (ПЗЗ). 
В них комментарии жителей города были застенографированы, проклассифицированы (за/против) и нанесены на карту. 

Файл: geo.xlsx
- x, y - координаты адреса, по которому был дан определённый комментарий
- comment_class - за (1) / против (-1)

Обязательные задания:
- визуально разделить город на районы безотносительно голосов (провести кластеризацию и вывести картинку) - использован KMeans
- аналогично исследовать скопления голосов за и против отдельно
- подобрать оптимальное число кластеров 

Дополнительные задания:
- найти наиболее активные в голосовании районы (подсказка: DBSCAN, неплотные районы обозначены одной меткой и закрашены одним цветом, cmap='gray')
- выделить основные тематики комментариев жителей, можно использовать всю имеющуюся дополнительную информацию. (была использована мера TF-IDF)

# (#12) «Улучшение качества модели» (GridSearchCV)
Взять boston house-prices dataset (sklearn.datasets.load_boston) и сделать то же самое для задачи регрессии 
(попробовать разные алгоритмы, поподбирать параметры, вывести итоговое качество):
- обучение модели регрессора методом KNN
- обучение модели линейной регрессии
- подбор оптимальных параметров регрессора с использованием GridSearchCV. 
(В качестве регрессора использованы RandomForestRegressor, DecisionTreeRegressor и ExtraTreeRegressor)

# Модуль ZAK-8 (Работа с заказчиком)
# (#2) «Методология ведения DS-проектов»
Возьмите задачу с винами (https://www.kaggle.com/datasets/rajyellow46/wine-quality) и решите ее, оформив в виде CrispDM-подхода
