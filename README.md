Порівняльний аналіз продуктивності контейнерних бекенд-сервісів на платформах Node.js та Python при змішаних навантаженнях
  
Проєкт реалізований для **багатокритеріальної оцінки** продуктивності двох фреймворків - Node, Python.
**Призначений** для фахівців, адже спрощує і прискорює вибір оптимального рішення під вимоги проєкту.
  
Архітектура системи побудована за принципом багаторівневої контейнеризованої архітектури та складається з:
1. Рівня вебсервісів (FastAPI і Node.js);
2. рівня контейнеризації Docker;
3. рівня навантажувального тестування на базі Locust (Endurance Testing та Experimental Method);
4. рівня аналітичної обробки результатів;
5. рівня багатокритеріального прийняття рішень із використанням методу TOPSIS.
Це абезпечує відтворюваність експериментів, об'єктивне порівняння зазначених альтернатив і комплексну оцінку продуктивності.
  
  
**Запуск**  
- Клонування  
  git clone repository  
  cd repository  
  
- Завантаження всіх бібліотек  
  pip install -r requirements.txt  
  
- Запуск контейнерів  
  docker compose up -d  
  docker compose build  
  Перевірка: docker ps  
  
- Перевірка доступності сервісів  
  FastAPI: http://localhost:8000  
  Node: http://localhost:3000  
  
- Встановлення Locust  
  pip install locust  
  
- Запуск експериментального методу тестування  
  powershell -ExecutionPolicy Bypass -File .\run_all.ps1  
  
- Запуск аналізу експериментального методу  
  python analyze.py  
  python analyze_plots.py  
  
- Запуск Endurance Testing (60 хв)  
  Запуск одного Python фреймворка: .\run_test.ps1 -FRAMEWORK python -CONCURRENCY 100 -DURATION_MIN 60  
  Запуск послідовно двох: .\run_all_endurance.ps1  
  
- Запуск аналізу Endurance Testing  
  Запуск одного Node фреймворка: python analyze_endurance.py node  
  Запуск послідовно двох: python analyze_endurance.py  
  
- Запуск TOPSIS аналізу  
  Класичний: python classic_topsis.py ` --data results/final_results.csv ` --output results  
  З візуалізацією: python visualize_topsis.py ` --data results/final_results.csv ` --output topsis_plots   
