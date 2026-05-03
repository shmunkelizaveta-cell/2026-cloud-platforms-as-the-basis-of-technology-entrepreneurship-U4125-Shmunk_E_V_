University: ITMO University

Faculty: FICT

Course: Cloud platforms as the basis of technology entrepreneurship ADD link

Year: 2026

Group: U4125

Author: Shmunk Elizaveta Vladimirovna

Lab: Lab2

Date of create: 03.05.2026

Date of finished: 03.05.2026


Ход работы
1. 
Был создан сервис в Google Cloud Run. При создании выбрала минимальные ресурсы:
CPU: 1
Memory: 128 MiB

<img width="848" height="556" alt="Снимок экрана 2026-05-03 в 17 25 27" src="https://github.com/user-attachments/assets/480fea74-2f50-4e81-a579-1d8e56adc95e" />

2. 
После развертывания сервис получил URL для доступа. Сервис успешно открылся. 
<img width="1380" height="814" alt="Снимок экрана 2026-05-03 в 17 19 56" src="https://github.com/user-attachments/assets/733d4e12-d179-48fd-847c-a7569a82d3c5" />

3. 
В разделе логов никаких ошибок нет, контейнер успешно запущен и работает корректно. Также были проанализированы метрики. 

<img width="972" height="285" alt="Снимок экрана 2026-05-03 в 17 21 16" src="https://github.com/user-attachments/assets/dc320a63-4ab5-4e32-87ff-b4cc9dba2c10" />

4. 
Был изменен порт контейнера с 8080 на 8090.
После изменения также видно, что сервис успешно открывается:
<img width="1440" height="816" alt="Снимок экрана 2026-05-03 в 17 25 16" src="https://github.com/user-attachments/assets/b5910cd2-3700-48a0-824d-2e3762b9f2b3" />

7. Переключение трафика между версиями
При распределении трафика не наблюдается резких изменений в нагрузке и скорости ответа сервиса.

<img width="1439" height="815" alt="Снимок экрана 2026-05-03 в 17 24 42" src="https://github.com/user-attachments/assets/10e1da5c-e447-4911-9fa0-b0a596b6d61f" />
8. Оба сервиса открываются по ссылке и работают нормально. Метрики показали стабильную работу, нагрузка распределяется равномерно,  ошибок нет. 
После этого сервис был удалён.
Вывод
В ходе лабораторной работы были изучены принципы работы Cloud Run, процесс развертывания контейнерных приложений, а также влияние параметров конфигурации (порт, трафик) на работоспособность сервиса.
