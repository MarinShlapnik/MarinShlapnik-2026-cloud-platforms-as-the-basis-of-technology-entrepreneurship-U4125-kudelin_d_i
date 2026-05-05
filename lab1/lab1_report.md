# Лабораторная работа №1: Обзор Google Cloud и исследование основных сервисов

## Информация о работе

| Параметр | Значение |
|----------|----------|
| **University** | ITMO University |
| **Faculty** | FICT |
| **Course** | Cloud platforms as the basis of technology entrepreneurship |
| **Year** | 2026 |
| **Group** | U4125 |
| **Author** | Kudelin Dmitry Igorevich |
| **Lab** | Lab1 |
| **Date of create** | 05.05.2026 |
| **Date of finished** | 05.05.2026 |

---

## Ход выполнения работы

### 1. Создание Service Account

На вкладке **Service Accounts** в Google Cloud Platform был создан сервисный аккаунт с именем `dkudelin-sa-lab1@cloud-platforms-as-the-basis.iam.gserviceaccount.com` с ролью **Storage Admin**, которая предоставляет полный доступ к облачному хранилищу.

**Скриншот Service Accounts:**

![Service Accounts](./screenshots/1_service_accounts.png)

### 2. Создание виртуальной машины

Далее была создана виртуальная машина в **Compute Engine** со следующими параметрами:
- **Имя**: `dkudelin-vm-lab1`
- **Тип машины**: `e2-micro` (минимальный вариант для снижения затрат)
- **Режим**: `Spot` (экономный режим)
- **Зона**: `us-central1-c`

**Скриншот VM Instances:**

![VM Creation](./screenshots/2_vm_instances.png)

### 3. Копирование файлов из облачного хранилища

После создания VM было выполнено подключение через SSH и использована утилита `gcloud` для поиска и копирования файлов из бакета `lab1-bucket-itmo` на локальную директорию виртуальной машины.

**Команда:**
```bash
gcloud storage cp gs://lab1-bucket-itmo/* .
