# ansible_test

Репозиторий - результат исполнения тестового задания по ролям ansible. 
Цель - установка, первичная настройка и запуск клиента openvpn на сервере ubuntu xenial.

## Установка

Для скачивания кода проекта к себе в консоли необходимо выполнить:

```
git clone https://github.com/klimarbeit/ansible_test.git
```


## Конфигурирование

* В файле **ansible_test/host_vars/client1.yml** значение переменной *ansible_host* нужно заменить на ip-адрес хоста, на котором будет происходить установка
* В файле **ansible_test/group_vars/openvpn_client88.yml** заменить значение переменной *ansible_user* на имя пользователя, под которым будет логинится **ansible** на целевой хост
* Добавить ключ текущего пользователя на хосте с **ansible** в *~/.ssh/authorized_keys* пользователя *ansible_user* на целевом хосте

## Запуск

Для запуска сценария находясь в папке проекта нужно выполнить

```
ansible-playbook --ask-vault-pass -i openvpn_inventory openvpn.yml
```

На приглашение 
```
Vault password:
```
ввести пароль **dGXY7vYUFKxilJVc** - им шифруется содержимое приватного ключа в конфиге клиента.

