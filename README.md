- Docker, PowerShell
docker compose up --build
docker compose build --no-cache
docker compose down


- powershell -ExecutionPolicy Bypass -File .\run_all.ps1


- python analyze.py

- python analyze_plots.py


(python -m pip install seaborn matplotlib pandas numpy)


В іншому PowerShell:
locust -f locustfile_node.py --headless -u 250 -r 25 --run-time 2m


- Endurance Test (60 хв)

.\run_test.ps1 -FRAMEWORK python -CONCURRENCY 100 -DURATION_MIN 60
.\run_test.ps1 -FRAMEWORK node -CONCURRENCY 100 -DURATION_MIN 60



run_test_endurance.ps1


.\run_all_endurance.ps1

python analyze_endurance.py node



Check monitor_metrics file
.\monitor_metrics.ps1 node results



- TOPSIS

python classic_topsis.py ` --data results/final_results.csv ` --output results

python visualize_topsis.py ` --data results/final_results.csv ` --output topsis_plots
