**University:** ITMO University

**Faculty:** FICT

**Course:** Cloud platforms as the basis of technology entrepreneurship ADD link

**Year:** 2026

**Group:** U4125

**Author:** Shmunk Elizaveta Vladimirovna

**Lab:** Lab1

**Date of create:** 01.05.2026

**Date of finished:** 01.05.2026


**Ход выполнения работы**
На вкладке Service Accounts в Google Cloud Platform был создан сервисный аккаунт eshmunk-sa-lab1@cloud-platforms-as-the-basis.iam.gserviceaccount.com
<img width="1440" height="761" alt="Снимок экрана 2026-05-04 в 14 34 58" src="https://github.com/user-attachments/assets/6fb56b43-ec09-45e0-8341-8d7040cac7c8" />
Далее была создана виртуальная машина в Compute Engine 
<img width="1440" height="813" alt="Снимок экрана 2026-05-04 в 15 35 38" src="https://github.com/user-attachments/assets/bbb800df-4af3-445a-94ab-fe117fc6d335" />

После этого с использованием утилиты gsutil был найден бакет lab1-bucket-itmo, и из него были скопированы файлы на локальную директорию виртуальной машины.
<img width="1440" height="92" alt="Снимок экрана 2026-05-04 в 14 56 35" src="https://github.com/user-attachments/assets/f49fc92f-2ef8-4bb5-b0f5-ebcfc31fab2d" />
<img width="1423" height="290" alt="Снимок экрана 2026-05-04 в 14 56 13" src="https://github.com/user-attachments/assets/ee36f49a-8e5d-4c67-938a-c24ad1f71427" />
На следующем этапе были изменены права доступа для созданного service account:
роль Storage Admin была заменена на Compute Viewer
<img width="1181" height="364" alt="Снимок экрана 2026-05-04 в 14 59 41" src="https://github.com/user-attachments/assets/1f6bade9-872a-4048-b4c3-869fb093e6e4" />
После изменения прав была предпринята повторная попытка копирования файлов. Несмотря на изменение роли, файлы продолжили успешно скачиваться и обновляться.
<img width="1426" height="345" alt="Снимок экрана 2026-05-04 в 15 06 01" src="https://github.com/user-attachments/assets/b0785319-5160-49f5-be01-b90d7a4792d1" />

Далее виртуальная машина была остановлена, и при её редактировании было обнаружено, что изначально использовался другой service account (по умолчанию). После этого был выбран созданный ранее service account.
<img width="1439" height="812" alt="Снимок экрана 2026-05-04 в 15 07 57" src="https://github.com/user-attachments/assets/0e07dacd-b7c5-4ff6-8090-a12ebdfa44b9" />
Но даже после этого доступ к бакету сохранялся, и файлы продолжали скачиваться.
<img width="1416" height="330" alt="Снимок экрана 2026-05-04 в 15 12 27" src="https://github.com/user-attachments/assets/deea5b0a-b1cd-4c71-92ff-788e39603a0f" />

После настроек доступа непосредственно у бакета, было обнаружено, что у группы allUsers стоит роль StorageObjectViewer, что означает публичный доступ. После удаления прав для allUsers повторная попытка доступа к бакету завершилась ошибкой — скачивание файлов стало невозможным.
<img width="1434" height="182" alt="Снимок экрана 2026-05-04 в 15 20 26" src="https://github.com/user-attachments/assets/047c6ab4-8e6f-40cf-9bac-6a4c1740c0d9" />
Затем публичный доступ был восстановлен, и возможность скачивания файлов снова появилась.

<img width="883" height="497" alt="Снимок экрана 2026-05-04 в 15 27 49" src="https://github.com/user-attachments/assets/54d93642-5be8-4757-9cd4-2a50dc435692" />

В завершение работы виртуальная машина была остановлена и удалена.
<img width="1438" height="807" alt="Снимок экрана 2026-05-04 в 15 29 30" src="https://github.com/user-attachments/assets/4b69fd3b-5082-4632-b5d8-d436334c7ec8" />

