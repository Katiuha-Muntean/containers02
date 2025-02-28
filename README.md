# **Лаборатораня работа №3 "Первый контейнер"**
## Цель работы
Данная лабораторная работа знакомит с основами контейнеризации и подготавливает рабочее место для выполнения следующих лабораторных работ.
### Задание 
Установить Docker Desktop и проверить его работоспособность.

 ### Описание выполнения работы
 1. Создаем репозиторий `containers02` и клонируем его на компьютер. Для этого используем команду ```git clone ``` и переходим в нашу склонированную папку.
 2. Создаем в папке containers02 файл под названием Dockerfile и заполяем его следующим:
  ```shell
FROM debian:latest
COPY ./site/ /var/www/html/
CMD ["sh", "-c", "echo hello from $HOSTNAME"]
```
3. В этой же папке создаем еще одну папку site. В новой папке создауем файл index.html с произвольным содержимым.
4. Открываем терминал в папке containers02 и выполняем следующую команду:
   <img src="https://imgur.com/NOIpGpI.png"  >
  *Сколько времени создавался образ?* 13.7
5. Выполняем команду для запуска контейнера:
   ```shell
   docker run --name containers02 containers02
   ```
   После выполнения в консоли видим следующее ***hello from a86bab00e269***
 ![Image-1](https://imgur.com/0lf3JNs.jpg)
6. Удаляем контейнер и запускаем его снова, мы переходим в наш root и пишем следующие команды:
 ``` shell
cd /var/www/html/
ls -l
   ```
После выволненения мы видим разрешения пользовтеля root для файла index.html. При выводе видно, что файл доступен для выполнения и чтения всеми, но изменять его может только root.
 ![Image-1](https://imgur.com/5KFT0cG.jpg)
 
### Выводы
 В ходе лабораторной работы были изучены основные команды для работы с Docker, приобретены навыки создания и управления контейнерами, а также освоены методы их анализа.
 
### Используемые источники
[My link](https://moodle.usm.md/mod/assign/view.php?id=282116)
   
