## Laboratory work I

Данная лабораторная работа посвещена изучению утилит для разработки проектов

## Tasks

- [x] 1. Ознакомиться со ссылками учебного материала
- [x] 2. Выполнить инструкцию учебного материала
- [x] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

Устанавливаем переменные окружения, создаем альтернативную версию команды
```
$ export GITHUB_USERNAME=D-I-R  # Создание в окружении GITHUB_USERNAME переменной
$ export GIST_TOKEN=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX  # Создание в окружении GIST_TOKEN переменной
$ alias edit=nano  # создание псевдоним команды
```


Создаем каталог workspace, который будет рабочей областью
```ShellSession
$ mkdir -p ${D-I-R}/workspace # создае каталога
$ cd ${D-I-R}/workspace  # переход в каталог
$ pwd # вывод пути в текущий каталог
#/home/pcd08/D-I-R/workspace
$ cd ..  # переход на директорию выше
$ pwd # вывод пути в текущий каталог
#/home/pcd08/D-I-R
```


В каталоге рабочей области создаем новые каталоги
```ShellSession
$ mkdir -p workspace/tasks/  # создание каталога
$ mkdir -p workspace/projects/ # создание каталога
$ mkdir -p workspace/reports/ # создание каталога
$ cd workspace # смена текущего каталога
```



Скачивание и распаковка node js
```ShellSession
# Debian
$ wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz  # загрузка архива
--2019-03-04 18:41:12--  https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz
Распознаётся nodejs.org (nodejs.org)… 104.20.22.46, 104.20.23.46, 2606:4700:10::6814:172e, ...
Подключение к nodejs.org (nodejs.org)|104.20.22.46|:443... соединение установлено.
HTTP-запрос отправлен. Ожидание ответа… 200 OK
Длина: 9356460 (8,9M) [application/x-xz]
Сохранение в: «node-v6.11.5-linux-x64.tar.xz»

node-v6.11.5-linux-x64.tar. 100%[=========================================>]   8,92M  6,32MB/s    in 1,5s    

2019-03-04 18:41:12 (6,32 MB/s) - «node-v6.11.5-linux-x64.tar.xz» сохранён [9356460/9356460]
$ tar -xf node-v6.11.5-linux-x64.tar.xz # разархивация
$ rm -rf node-v6.11.5-linux-x64.tar.xz # удаление архива
$ mv node-v6.11.5-linux-x64 node # переименование файла
```



Добавляем в PATH путь к скачанному файлу
```ShellSession
$ ls node/bin # вывод на экран содержимого 
node  npm
$ echo ${PATH} # отображение содержимого переменной PATH
/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games:/usr/lib/jvm/java-8-oracle/bin:/usr/lib/jvm/java-8-oracle/db/bin:/usr/lib/jvm/java-8-oracle/jre/bin
$ export PATH=${PATH}:`pwd`/node/bin # присвоение переменной среды PATH новое значение
$ echo ${PATH} # отображает содержимое переменной PATH
$ mkdir scripts
$ cat > scripts/activate<<EOF  # копирование в файл содержимого переменной PATH c измененным значением
export PATH=\${PATH}:`pwd`/node/bin
EOF
$ source scripts/activate # чтение и выполнение команды из файла в текущей среде
```



Устанавливаем пакет gistup в каталог скачанного файла
```ShellSession
$ npm install -g gistup # установка gistup
/home/pcd08/D-I-R/workspace/node/bin/gistup -> /home/pcd08/D-I-R/workspace/node/lib/node_modules/gistup/bin/gistup
/home/pcd08/D-I-R/workspace/node/bin/gistup-open -> /home/pcd08/D-I-R/workspace/node/lib/node_modules/gistup/bin/gistup-open
/home/pcd08/D-I-R/workspace/node/bin/gistup-rename -> /home/pcd08/D-I-R/workspace/node/lib/node_modules/gistup/bin/gistup-rename
/home/pcd08/D-I-R/workspace/node/lib
└─┬ gistup@0.1.3 
  ├─┬ optimist@0.3.7 
  │ └── wordwrap@0.0.3 
  └── queue-async@1.2.1 
$ ls node/bin # вывод на экран содержимого
gistup  gistup-open  gistup-rename  node  npm
```



Настройка конфига модуля gistup
```ShellSession
$ cat > ~/.gistup.json <<EOF # запись в файл токен
{
  "token": "${GIST_TOKEN}"
}
EOF
```

## Report

```ShellSession
$ export LAB_NUMBER=01
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gistup -m "lab${LAB_NUMBER}" # enter: yes↵
```

## Links

### Unix commands

- [ar](https://en.wikipedia.org/wiki/Ar_(Unix))
- [cat](https://en.wikipedia.org/wiki/Cat_(Unix))
- [cd](https://en.wikipedia.org/wiki/Cd_(command))
- [cp](https://en.wikipedia.org/wiki/Cp_(Unix))
- [cut](https://en.wikipedia.org/wiki/Cut_(Unix))
- [echo](https://en.wikipedia.org/wiki/Echo_(command))
- [env](https://en.wikipedia.org/wiki/Env_(shell))
- [ex](https://en.wikipedia.org/wiki/Ex_(editor))
- [file](https://en.wikipedia.org/wiki/File_(command))
- [find](https://en.wikipedia.org/wiki/Find)
- [ls](https://en.wikipedia.org/wiki/Ls)
- [man](https://en.wikipedia.org/wiki/Man_page)
- [mkdir](https://en.wikipedia.org/wiki/Mkdir)
- [mv](https://en.wikipedia.org/wiki/Mv)
- [nm](https://en.wikipedia.org/wiki/Nm_(Unix))
- [ps](https://en.wikipedia.org/wiki/Ps_(Unix))
- [pwd](https://en.wikipedia.org/wiki/Pwd)
- [rm](https://en.wikipedia.org/wiki/Rm_(Unix))
- [sed](https://en.wikipedia.org/wiki/Sed)
- [touch](https://en.wikipedia.org/wiki/Touch_(Unix))

### Package Managers

- [apt](http://help.ubuntu.ru/wiki/apt) | [dnf](https://en.wikipedia.org/wiki/DNF_(software)) | [yum](https://fedoraproject.org/wiki/Yum/ru)
- [brew](https://brew.sh) | [linuxbrew](http://linuxbrew.sh)
- [npm](https://docs.npmjs.com)

### Software

- [curl](https://www.gitbook.com/book/bagder/everything-curl/details)
- [wget](https://www.gnu.org/software/wget/manual/wget.pdf)
- [clang](https://clang.llvm.org)
- [g++](https://gcc.gnu.org/onlinedocs/gcc-4.0.2/gcc/G_002b_002b-and-GCC.html)
- [make](https://en.wikipedia.org/wiki/Make_(software))
- [open](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/open.1.html)
- [openssl](https://www.openssl.org)
- [nano](https://www.nano-editor.org)
- [tree](https://linux.die.net/man/1/tree)
- [vim](http://www.vim.org)

## Homework

1. Скачайте библиотеку *boost* с помощью утилиты **wget**. Адрес для скачивания `https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`.
2. Разархивируйте скаченный файл в директорию `~/boost_1_69_0`
3. Подсчитайте количество файлов в директории `~/boost_1_69_0` **не включая** вложенные директории.
4. Подсчитайте количество файлов в директории `~/boost_1_69_0` **включая** вложенные директории.
5. Подсчитайте количество заголовочных файлов, файлов с расширением `.cpp`, сколько остальных файлов (не заголовочных и не `.cpp`).
6. Найдите полный пусть до файла `any.hpp` внутри библиотеки *boost*.
7. Выведите в консоль все файлы, где упоминается последовательность `boost::asio`.
8. Скомпилирутйе *boost*. Можно воспользоваться [инструкцией](https://www.boost.org/doc/libs/1_61_0/more/getting_started/unix-variants.html#or-build-custom-binaries) или [ссылкой](https://codeyarns.com/2017/01/24/how-to-build-boost-on-linux/).
9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.
10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
11. Найдите *топ10* самых "тяжёлых".

```
Copyright (c) 2015-2019 The ISC Authors
```
