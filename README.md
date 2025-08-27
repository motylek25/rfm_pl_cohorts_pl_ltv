# RFM + Cohort Retention + LTV

Короткий учебный проект по продуктовой аналитике: по транзакциям магазина считаем RFM‑сегменты, строим когортный retention и кумулятивный LTV. Ноутбук устойчив к разным CSV (автодетект кодировки/разделителя, нормализация имён колонок).

Что делает
- Загружает CSV, приводит даты и числа, исключает возвраты, формирует user_id.
- RFM: Recency/Frequency/Monetary, квантильный биннинг (1–4), общий RFM‑скор.
- Cohorts: cohort_month, cohort_index, retention‑матрица (читабельные подписи, без «0%», фильтр по размеру когорты и числу месяцев).
- LTV: кумулятивная выручка/клиента; подавление выбросов (winsorize); график «медиана + топ‑когорты».
- Сохраняет артефакты: rfm_table.csv, rfm_segments_summary.csv, retention_pivot.csv, ltv_pivot.csv.

Как запустить
1) Установить зависимости:
   ```
   pip install pandas numpy seaborn matplotlib
   ```
2) Открыть ноутбук rfm_cohorts_ltv.ipynb (Jupyter/Colab).
3) В ячейке загрузки указать путь к файлу:
   ```python
   FILE = "online_retail_ii.csv"  # ваш CSV
   ```
