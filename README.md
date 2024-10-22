# Домашнее задание к занятию 10 «Jenkins»

## Основная часть

1. Сделать Freestyle Job, который будет запускать `molecule test` из любого вашего репозитория с ролью.
   
![img](https://github.com/SeNike/Study_24/blob/main/ansible-02/j1.png)
![img](https://github.com/SeNike/Study_24/blob/main/ansible-02/j2.png)

2. Сделать Declarative Pipeline Job, который будет запускать `molecule test` из любого вашего репозитория с ролью.

![img](https://github.com/SeNike/Study_24/blob/main/ansible-02/j3.png)
![img](https://github.com/SeNike/Study_24/blob/main/ansible-02/j4.png)

3. Перенести Declarative Pipeline в репозиторий в файл `Jenkinsfile`.

![img](https://github.com/SeNike/Study_24/blob/main/ansible-02/j5.png)
![img](https://github.com/SeNike/Study_24/blob/main/ansible-02/j6.png)
   
4. Создать Multibranch Pipeline на запуск `Jenkinsfile` из репозитория.

![img](https://github.com/SeNike/Study_24/blob/main/ansible-02/j7.png)
![img](https://github.com/SeNike/Study_24/blob/main/ansible-02/j8.png)

5. Создать Scripted Pipeline, наполнить его скриптом из [pipeline](./pipeline).
6. Внести необходимые изменения, чтобы Pipeline запускал `ansible-playbook` без флагов `--check --diff`, если не установлен параметр при запуске джобы (prod_run = True). По умолчанию параметр имеет значение False и запускает прогон с флагами `--check --diff`.
7. Проверить работоспособность, исправить ошибки, исправленный Pipeline вложить в репозиторий в файл `ScriptedJenkinsfile`.
8. Отправить ссылку на репозиторий с ролью и Declarative Pipeline и Scripted Pipeline.
9. Сопроводите процесс настройки скриншотами для каждого пункта задания!!

## Необязательная часть

1. Создать скрипт на groovy, который будет собирать все Job, завершившиеся хотя бы раз неуспешно. Добавить скрипт в репозиторий с решением и названием `AllJobFailure.groovy`.
2. Создать Scripted Pipeline так, чтобы он мог сначала запустить через Yandex Cloud CLI необходимое количество инстансов, прописать их в инвентори плейбука и после этого запускать плейбук. Мы должны при нажатии кнопки получить готовую к использованию систему.
