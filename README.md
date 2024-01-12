# Git instruction
_Система контроля версий_

### Для чего?
* Хранить, изменять, анализировать версии проекта
* Объединять результаты работ команды
___

## Где работать с Git
_Терминал (консоль, командная строка)_

_**macOS / Linux**_  
1. Запустить программу _Terminal_

_**Windows**_
1. На официальном сайте _[Git](https://git-scm.com/download/win "Git")_, скачать одну из версий категории _Standalone Installer_
2. Установить программу обращая внимание на пункт _Git Bash Here_ (включение его позволить терминалу с Git открыться в любой папке)
3. Запустить программу _Git Bash_

---

## Базовые команды терминала

**Полезное**  
- Для выполнения команд использовать _Enter_  
- Для использования нескольких команд, их нужно разделять ```&&```  
- Для обращения к последней используемой команде _стрелка вверх_  
Двойное нажатие вернет предпоследнюю команду  
Для возвращения команды _стрелка вниз_
- Для автозаполнения команды или пути _Tab_  

### Команды

```pwd``` — вывести текущую рабочую директорию  

**Список**  

```ls``` — вывести содержимое директории  
```ls ~``` — вывести содержимое домашней директории  
```ls ..``` — вывести содержимое родительской директории (_директории уровнем выше_)  
```ls -a``` — вывести расширенный список содержимого директории (_все скрытые файлы_)

**Навигация**  

```cd``` — сменить директорию  
```cd ~``` — перейти к домашней директории  
```cd .``` — перейти в текущую директорию  
```cd ..``` — вернуться в родительскую директорию  
```cd /``` — перейти в корневую директорию

**Примитивные действия**  

```touch``` — создать файл в текущей директории  
```touch ~``` — создать файл в домашней директории  
```touch ..```— создать файл в родительской директории  

```mkdir``` — создать директорию (_папку_) в текущей директории  
```mkdir -p``` — создать структуру директорий  
```mkdir ~``` — создать директорию в домашней директории  
```mkdir ..``` — создать директорию в родительской директории  

```cp``` — копировать файл  
```cp ~``` — скопировать файл в домашнюю директорию  
```cp ..``` — скопировать файл в родительскую директорию  

```mv``` — переместить файл или папку  
```mv ~``` — переместить в домашнюю директорию  
```mv ..``` — переместить в родительскую директорию  

```cat``` — распечатать содержимое текстового файла  

```rm``` — удалить файл из текущей папки  
```rmdir``` — удалить пустую директорию  
```rm -r``` — удалить невзирая на то, что в директории есть содержимое  

---

## Установка Git
**_macOS_**  
_Первый способ_
1. В терминале выполнить команду ```/usr/bin/git```
2. Установить _Git_
3. Проверить командой ```git version```  

_Второй способ_
1. На официальном сайте [Homebrew](https://brew.sh/ "Homebrew"), скопировать команду для установки
2. Найти _Terminal_, в него поместить и запустить скопированную ранее команду
3. Установить _Git_ с помощью _Homebrew_, запустив команду ```brew install git```
4. Проверить командой ```git version```  

**_Linux_**
1. На официальном сайте [Git](https://git-scm.com/download/linux "Git") выбрать команду установки для своей версии Linux
2. Скопировать и запустить эту команду в терминале
3. Проверить командой ```git version```

**_Windows_**
1. Git уже установлен вместе с терминалом
2. Проверить командой ```git version```

---
## Команды Git
### Настройка Git
 Все глобальные настройки хранятся в файле _.gitconfig_  

```git config --global``` - вносит персональные данные (имя ```user.name```, почта ```user.email```)

### Git - репозиторий
```git init``` — сделать текущую папку репозиторием  
``rm -rf .git`` — "разгитить" папку

**Ключи**  
```-r``` — позволяет удалять папки вместе с их содержимым  
```-f``` — избавляет от подтверждений об удалении 

```git status``` — проверка состояния репозитория  
```git add``` — подготовить файл к сохранению в репозиторий  
```git add --all``` — подготовить к сохранению все имеющиеся файлы  
```git add .``` — добавить всю текущую папку в репозиторий  

```git commit``` — выполнить коммит (сохранение)  
```git commit -m```— присвоить коммиту пояснительное сообщение  
```got log``` — посмотреть историю коммитов  

<br>
<br>
<br>

# GitHub
_Платформа, которая работает с Git и упрощает командное взаимодействие_
### Для чего?
- Создание, хранение и удаление удаленного репозитория
- Совместная работа

---

## Удаленный репозиторий
### Создание
1. Зайти на GitHub по ссылке https://github.com/<username> (username - имя указанное при регистрации)
2. Создать репозиторий во вкладке _Repositories_, и дать ему название

---

## Связка удаленного репозитория с локальным
*Для связки репозиториев используется SSH*

**SSH** — протокол, обеспечивающий безопасный обмен данных в сети и использует для этого ключи  
**SSH-ключ** — виртуальный идентификатор GitHub позволяющий получить доступ к GitHub-репозиторию  
**SSH-ключ** — публичный (зашифрует данные) и приватный (расшифрует данные)

```cd ~ && ls -la .ssh/``` — проверить наличие ключей  

### Генерация SSH-ключа
1. Использовать программу _ssh-keygen_  
```ssh-keygen -t ed25519 -C "электронная почта, к которой привязан аккаунт на GitHub"```  
или  
```ssh-keygen -t rsa -b 4096 -C "электронная почта, к которой привязан аккаунт на GitHub"```
2. Указать место хранение ключа или сделать домашний каталог путем по умолчанию нажав _Enter_
3. Ввести кодовую фразу или оставить место пустым нажав _Enter_
4. Проверить сгенерировались ли ключи ```la -a ~/.ssh```

### Связка SSH-ключа с GitHub
_Созданные ключи хранятся в директории ```~/.ssh```_

1. Скопировать содержимое файла с публичным ключом в буфер обмена  
_**macOS**_  
```pbcopy < ~/.ssh/id_номер или название.pub``` (_Скопировать в буфер обмена все содержимое файла ~/.ssh/id_rsa.pub_)  
_**Windows**_  
```clip < ~/.ssh/id_номер или название.pub``` или ```cat ~/.ssh/id_номер или название.pub```
2. На GitHub в настройках выбрать _SSH and GPG keys_ и создать новый ключ
3. Дать название ключу и вставить скопированный ранее ключ
4. Проверить правильность ключа ```ssh -T git@github.com```
 
### Связка репозиториев 
_На странице репозитория в GitHub необходимо скопировать URL выбрав тип SSH_

```git remote add``` — привязать удаленный репозиторий к локальному  

```git remote add origin git@github.com:имя аккаунта/first-project.git ```  

```git remote -v``` — убедиться, что репозитории связаны  

---

## Синхронизация локального репозитория с удаленным

```git push``` — отправить изменения на удаленный репозиторий (_В первый раз эту команду нужно вызвать с флагом ```-u```_)  
```-u``` — свяжет локальную ветку с одноименной удаленной

---
## Хэш
_Основной идентификатор коммита_

**Хеш** — короткая строка, которая состоит из цифр 0—9 и латинских букв A—F

- если хеш получить дважды для одного и того же набора входных данных, то результат будет гарантированно одинаковый
- если хоть что-то в исходных данных поменяется (хотя бы один символ), то хеш тоже изменится 

---
## Описание коммита
### log
```git log``` — показать историю коммитов
- commit (хеш коммита)
- autor
- date
- само сообщение коммита  

```git log --oneline```— показать сокращенную историю коммитов  
- одна строка
- сокращенные хеши  

### Файл HEAD  
_Служебный файл папки .git_, указывающий на последний коммит  

```cd .git/ && ls``` — перейти в папку и показать ее содержимое  
```cat HEAD``` — распечатать содержимое файла (внутри ссылка на хеш)

---

## Статусы файлов Git

- **untracked** — не отслеживаемый (перед ```git add```)
- **staged** — подготовленный (после ```git add```)
- **tracked** — отслеживаемый (после ```git commit```)
- **modified** — измененный  

### Жизненный цикл файла Git

```mermaid
graph LR;
  untracked -- "git add" --> staged;
  staged -- "git commit" --> tracked/comitted;
  tracked/comitted -- "изменения" --> modified;
  modified -- "git add" --> staged;
  staged --> modified;
```
---


