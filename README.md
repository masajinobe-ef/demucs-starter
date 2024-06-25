# demucs-starter

## Установка

Для установки потребуется [Poetry](https://python-poetry.org/docs/#installing-with-the-official-installer) и [Python](https://www.python.org/):

```sh
(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | py -
```

Скопируйте репозиторий на локальную машину:

```sh
git clone https://github.com/masajinobe-ef/demucs-starter.git
```

Перейдите в папку demucs-starter с помощью PowerShell и введите следующие команды для настройки окружения:

```sh
cd demucs-starter
poetry config virtualenvs.in-project true
poetry shell
poetry install
```

Для запуска изоляции расположите ваш .mp3 файл в папку demucs-starter и запустите скрипт:

```sh
.\start.ps1
```

### Настройка скрипта

```sh
Get-ChildItem *.mp3 | foreach { demucs -d cpu -n htdemucs_ft --two-stems=vocals --overlap 0.1 --mp3 $_.FullName }
```

Модели:

- htdemucs - Стандартная модель.
- htdemucs_ft - Дольше, но лучше.

Инструменты:

- drums
- bass
- other
- vocals

Форматы:

- .wav
- .mp3
