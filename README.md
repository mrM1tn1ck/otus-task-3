<img src="https://velog.velcdn.com/images/lijahong/post/17d92501-2210-4efb-a26a-f1eea7233acc/image.png"/>

## Описание
---
Создание 2 ВМ с помощью Vagrant. 
Установка и настройка NGINX с помощью Ansible

## Запуск
---
- Клонируем репозиторий `git clone https://github.com/mrM1tn1ck/otus-task-3.git`
- Выполняем команду `vagrant up` из директории проекта

## Установка и настройка NGINX
---
Представленный Vagrantfile создаст 2 ВМ на VirtualBox. 
1-ая ВМ в роли управляющей машины, 2-ая ВМ для развертывания NGINX.
Будут установлены все необходимые зависимости, обновления системы и Ansible.
Для взаимодействия с хостом для Ansible сгенерированы SSH ключи. 
Далее необходимо:
1. зайти в систему выполнив команду `vagrant ssh ansible`
2. перейти в каталог `/vagrant/ansible/` 
3. для установки и настройки NGINX выполняем следующую команду:
```
ansible-playbook nginx.yml
```

## Проверка работоспособности NGINX
---
Для проверки работоспособности с управляющей машины запускаем команду
```
curl 192.168.10.10:8080
```
где можно будет увидет HTML код страницы приветсвия NGINX