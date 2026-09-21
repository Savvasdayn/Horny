#!/usr/bin/env bash

read -p "Введите ваше имя: " name
echo "Привет, $name! Добро пожаловать в мир Bash!"


#!/usr/bin/env bash

read -p "Введите первое число: " num1
read -p "Введите второе число: " num2

sum=$((num1 + num2))
echo "Сумма: $sum"


#!/usr/bin/env bash

read -p "Введите число: " number

if (( number % 2 == 0 )); then
  echo "Число $number — чётное."
else
  echo "Число $number — нечётное."
fi


#!/usr/bin/env bash

PROJECT_NAME="my-project"

mkdir -p "$PROJECT_NAME/css"
mkdir -p "$PROJECT_NAME/js"

touch "$PROJECT_NAME/index.html"
touch "$PROJECT_NAME/css/style.css"
touch "$PROJECT_NAME/js/script.js"

echo "Структура проекта создана: $PROJECT_NAME"
tree "$PROJECT_NAME" 2>/dev/null || find "$PROJECT_NAME" -type d -print | sed 's/[^-][^\/]*\//|   /g' -e 's/|   \([^ ]\)/|__ \1/'


#!/usr/bin/env bash

LENGTH=8

# Используем /dev/urandom и tr для получения случайных символов
password=$(cat /dev/urandom | tr -dc 'A-Za-z0-9' | head -c "$LENGTH")

echo "Сгенерированный пароль: $password"


#!/usr/bin/env bash

EXTENSION="${1:-txt}"

echo "Ищем файлы с расширением .$EXTENSION в текущей директории..."

find . -maxdepth 1 -type f -name "*.${EXTENSION}"


chmod +x *.sh
sh 1.sh
sh 2.sh
# и так далее


# Bash-скрипты: самостоятельная работа

Набор Bash-скриптов для выполнения учебных заданий.

## Список скриптов

- `1.sh` — приветствие пользователя.
- `2.sh` — калькулятор суммы двух чисел.
- `3.sh` — проверка чётности числа.
- `4.sh` — создание структуры папок для веб-проекта.
- `5.sh` — подсчёт строк в файле.
- `6.sh` — генератор случайного пароля (8 символов).
- `7.sh` — поиск файлов по расширению.
- `github-stats.sh` — анализ статистики репозитория GitHub (WSL).

## Как запустить

1. Сделайте скрипты исполняемыми:
   ```bash
   chmod +x *.sh
