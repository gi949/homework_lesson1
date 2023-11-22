# homework_lesson1
Провести настройку аутентификации доступа к yandex cloud-id,
введя в консоли:

export YC_TOKEN=$(yc iam create-token)

export YC_CLOUD_ID=$(yc config get cloud-id)

export YC_FOLDER_ID=$(yc config get folder-id)


Ввести в консоли команды:

Инициализация terraform

terraform init

Проверка сценария terraform

terraform plan

Запустить сценарий создания ВМ vm-1

terraform apply

В консоле будут выведены 

внешний ip - external_ip_address_vm_1

и внутренний ip - internal_ip_address_vm_1


Перейти в папку ansible

В файле ya.yaml ввести external_ip_address_vm_1 для vm-1:

vm-1 ansible_host=<external_ip_address_vm_1>

Проверить доступность vm-1 с помощью модуля ping

ansible vm-1 -m ping

Проверить корректность синтаксиса плэйбука task.yaml

ansible-playbook --syntax-check task.yaml

Запустить плэйбук установки nginx на vm-1 task.yaml

ansible-playbook task.yaml

Для проверки запущен ли nginx на vm-1, выполнить

curl -I <external_ip_address_vm_1>

Код ответа 200 свидительствует о доступности nginx на порту 80
