# Работа с MariaDB
## Установка MariaDB
*Если СУБД MariaDB у вас не установлена, разверните разделы "Установка MariaDB на Линукс" и "Дополнительные настройки после установки"*
<details>
<summary>Установка MariaDB на Линукс</summary>
Для того чтобы нам установить MariaDB, необходимо:

  1) Скачать файл InstallMariaDBlinux.sh
  
2) Открыть папку с файлом, нажимаем ПКМ по свободному месту в папке и "открыть в терминале" or "Open in terminal"
  > ПКМ - Правая кнопка мыши
  3) Прописываем команду:
>**chmod a+x InstallMariaDBlinux.sh**
  >>с помощью команды "chmod", мы выдаем права для исполнения файла
  >>>Параметр "а" означает, что мы решаем ему изменять данные в компьютере
  >>>>Параметр "x" означает, что мы даем разрешение на выполнение
  4) Указываем абсолютный путь к файлу
>*Пример: /home/sashavoin5/Downloads/InstallMariaDBlinux.sh*
  
 5. После 4 шага начнется установка MariaDB на ваш компьютер, соглашайтесь установить вводя "y" в терминал и нажимая Enter
 Спустя непродолжительное время у вас должна открыться консоль MariaDB.
  Если вы видите что-то похожее с рисунком ниже  
  
  ![image](https://github.com/bondden/tododb/assets/99070683/57f818e8-be09-4511-a89f-7a68a56e929c)
  
✅ Поздравляю!!! Вы установили MariaDB
</details>

<details>
<summary>Дополнительные настройки после установки</summary>
Для полного комфорта, нужно сделать одну настройку:
  
  1) Нужно прописать команду
  
  >UPDATE mysql.user SET authentication_string=PASSWORD('rootPleshkov6') WHERE User='root';
  >>Вместо rootPleshkov6 вводите свой пароль
  2) И также прописать команду ***FLUSH PRIVILEGES;*** для обновления привилегий.
  3) После этого прописываем "Exit", чтобы выйти из консоли MariaDB
  4) Мы можем войти уже в наш новый аккаунт:
  > sudo mysql -u root -p 
  >>После вас сначала попросит вести пароль от аккаунта Linux (не всегда), потом от аккаунта MariaDB.
  >>> Сейчас входить в аккаунт необязательно                                                        
  

</details>

+ **Импорт данных**

  + После того как MariaDB у вас установлена, скачиваем файлы ***LexorankMariaDB.sql*** и ***TodoLex.tsv***
>В файле ***LexorankMariaDB.sql*** хранится скрипт, который сделает некоторые моменты
>>В файле ***TodoLex.tsv*** хранятся данные, которые скрипт восстановит

Откройте файл ***LexorankMariaDB.sql*** через текстовый редактор, нажав ПКМ и *'открыть через текстовый редактор'*
Вам нужно указать абсолютный путь до файла ***TodoLex.tsv***,где есть выделение:

![image](https://github.com/bondden/tododb/assets/99070683/9820be49-00cb-499d-8d7a-f67472417a86)

📩 Также необязательно, но вы можете поменять путь, куда будут сохраняться tsv и json файлы (последние две команды, указать в кавычках абсолютный путь до папки и названия файла)

После чего прописываем команду в терминале(выйдя из терминала MariaDB): 
> ***sudo mysql -u root -p < /home/sashavoin5/Downloads/LexorankMariaDB.sql***
>> Данная команда выполнит скрипт, вам нужно будет лишь указать пароль

После успешного выполнения скрипта, у вас должно получиться вот такое:
![image](https://github.com/bondden/tododb/assets/99070683/1c5f5765-0b75-405d-8461-050f6c6efc8b)
✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅✅

и сформированные файлы по вашему пути, которые вы указали (или по пути /var/lib/mysql если оставили стандартным)
>Директория /var/lib/mysql находится не в директории Home
>>Вам надо открыть проводник, Other Locations (внизу слева самое последнее)
>>>И в Other Locations вы уже найдете /var/lib/mysql




