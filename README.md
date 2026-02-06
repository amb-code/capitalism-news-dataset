# Capitalism news dataset

## News categories about social conflicts and contradictions of society

The dataset includes one negative class (0) and 12 positive classes (1-12) of news about the economy and society. For the convenience of building a classification algorithm, class 0 has been added to the dataset. Positive classes:

1. Protest (rus, Протест)
2. Workers’ struggle (rus, Борьба трудящихся)
3. Labor relations (rus, Трудовые отношения)
4. Living conditions (rus, Условия жизни)
5. Decline of sectors (rus, Упадок сфер)
6. Creditworthiness (rus, Закредитованность)
7. Inequality (rus, Неравенство)
8. Repression (rus, Репрессии)
9. Atlas Shrugged (rus, Будни Атлантов)
10. Economic relations (rus, Экономические отношения)
11. Combat operations (rus, Боевые действия)
12. Other (rus, Прочее)

Column description:

1. class : int {0,1,2,...12}
2. label : name of class
3. text : sentence
4. keywords : main words from text in normal form
5. url : news url internet link
6. class-validation: type of annotation check

## Sources
1. https://github.com/amb-code/capitalism-news-dataset
2. https://www.kaggle.com/datasets/ireshin/capitalism-news-dataset

## Collection methodology
Step 1: annotate by hand for multiclass task part of GDDR dataset (https://www.kaggle.com/datasets/ireshin/gddr-news).
Step 2: fit 4 BERT models (2 binary classificators [0 or >0], 2 multiclass models [0, 1, ..., 12]).
Step 3: take random kaggle news dataset and label it with 2 binary BERT classificators (from step 2), take ~60000 with class 0.
Step 4: throughout 2025 year, collect news from various global media outlets with urls and label it with 4 BERT models (from step 2), take ~10000 with class &gt;0.

RESULT ~100 000 news in dataset.
Result step 1: ~10000 news with class >0 (human-hand) and ~20000 news with class =0 (human-hand).
Result step 3: ~60000 news with class =0 (2x-BERT-ensemble).
Result step 4: ~10000 news with class >0 (4x-BERT-ensemble).
