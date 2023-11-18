# Тема 7.Работа с файлами (ввод, вывод)
Отчет по Теме #7 выполнил(а):
- Легков Иван Сергеевич
- ПИЭ-21-1

| Задание | Лаб_раб | Сам_раб |
| ------ | ------ | ------ |
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |
| Задание 6 | + | |
| Задание 7 | + | |
| Задание 8 | + |  |
| Задание 9 | + |  |
| Задание 10 | + |  |

# Лабараторные работы 
   ## Лабараторная работа 1


  ```python
Hello students
How are you?
```
  ### Результат
  
 ![1](https://github.com/armuane/laba7/blob/main/1.png?raw=true)

## Краткий вывод:

Мы написали текстовый файл в директрии программы 

   ## Лабараторная работа 2


  ```python
f=  open("input.txt", "r")
print(f.readline())
f.close()
```
  ### Результат
  ![2](https://github.com/armuane/laba7/blob/main/2.png?raw=true)

 
## Краткий вывод:
Этот код открывает файл с именем "input.txt" в режиме чтения ("r"), считывает первую строку из файла с помощью метода readline() и затем закрывает файл с помощью метода close().

Таким образом, первая строка из файла "input.txt" будет выведена на экран.


   ## Лабараторная работа 3


  ```python
f=  open("input.txt", "r")
print(f.readlines())
f.close()

```
  ### Результат
  ![3](https://github.com/armuane/laba7/blob/main/3.png?raw=true)

 
## Краткий вывод:
этом коде файл "input.txt" открывается в режиме чтения ("r"). Затем вызывается метод readlines(), который считывает все строки из файла и возвращает их в виде списка строк. Наконец, этот список строк выводится с помощью функции print(). После этого файл закрывается методом close().

Таким образом, на экран будет выведен список строк, содержащих все строки из файла "input.txt".


   ## Лабараторная работа 4


  ```python
with open("input.txt") as f:
    print(f.readlines())
```
  ### Результат
  ![4](https://github.com/armuane/laba7/blob/main/4.png?raw=true)

 
## Краткий вывод:
Этот код использует конструкцию with, которая автоматически управляет контекстом открытого файла. Файл "input.txt" открывается внутри блока with, и после выполнения блока кода файл автоматически закрывается.

Внутри блока with вызывается метод readlines(), который считывает все строки из файла и возвращает их в виде списка строк. Затем этот список строк выводится с помощью функции print().

Использование with обеспечивает правильное закрытие файла даже в случае исключения или других ошибок внутри блока кода, что делает код более безопасным.


   ## Лабараторная работа 5


  ```python
with open("input.txt") as f:
    for line in f:
      print(line)
```
  ### Результат
  ![5](https://github.com/armuane/laba7/blob/main/5.png?raw=true)

 
## Краткий вывод:
В данном коде также используется конструкция with для открытия файла "input.txt" в режиме чтения. Затем происходит итерация по строкам файла с использованием цикла for. На каждой итерации переменная line принимает значение следующей строки из файла, и эта строка выводится на экран с помощью функции print().

Таким образом, код выводит все строки из файла "input.txt" на экран, по одной строке за каждую итерацию цикла. Как и в предыдущем случае, конструкция with автоматически закрывает файл после завершения работы с ним.


   ## Лабараторная работа 6


  ```python
with open("input.txt","a+") as f:
   f.write("/nIm fine")
with open("input.txt","r") as f:
    result = f.readlines()
    print(result)
```
  ### Результат
  ![6](https://github.com/armuane/laba7/blob/main/6.png?raw=true)

 
## Краткий вывод:
В этом коде открывается файл "input.txt" в режиме добавления и чтения ("a+"). В режиме добавления ("a") файл открывается для записи, и если файл не существует, он будет создан. При этом курсор устанавливается в конец файла. Затем выполняется блок кода внутри первого with.

   ## Лабараторная работа 7


  ```python
lines = ["one","two","three"]
with open("input.txt","w") as f:
    for line in lines:
        f.write("\nCycle run "+ line)
    print("Done!")
```
  ### Результат
  ![7](https://github.com/armuane/laba7/blob/main/7.png?raw=true)


 
## Краткий вывод:



   ## Лабараторная работа 8


  ```python
import os

def print_docs(directory):
    all_files= os.walk(directory)
    for catalog in all_files:
        print(f"Папка{catalog[0]} содержит:")
    print(f'Директории: {", ".join([folder for folder in catalog[1]])}' )
    print(f'Файлы {", ".join([file for file in catalog[2]])}')
    print('-' * 40)

print_docs(" glush\Desktop\library")

```
  ### Результат
  ![8](https://github.com/armuane/laba7/blob/main/8.png?raw=true)

 
## Краткий вывод:
Код использует модуль os для просмотра содержимого указанной директории.


   ## Лабараторная работа 9


  ```python
def longest_words(file):
    with open(file, encoding = "utf-8") as f:
        words = f.read().split()
        max_length = len(max(words,key=len))
        for word in words:
            if len(word)== max_length:
                sought_words = word

        if len(sought_words)== 1:
            return sought_words[0]
        return sought_words

print(longest_words("input.txt"))
```
  ### Результат
  ![9](https://github.com/armuane/laba7/blob/main/9.png?raw=true)

 
## Краткий вывод:
Этот код читает содержимое файла "input.txt", разбивает его на слова и находит самые длинные слова в файле. 


   ## Лабараторная работа 10


  ```python
import csv
import datetime
import time
with open ('rows_300.csv','w', encoding= 'utf-8', newline='') as f:
    writer =csv.writer(f)
    writer.writerow(['№','Секунда','Микросекунда'])
    for line in range (1,301):
        writer.writerow([line,datetime.datetime.now().second,
                         datetime.datetime.now().microsecond])
        time.sleep(0.01)


```
  ### Результат
  ![10](https://github.com/armuane/laba7/blob/main/10.png?raw=true)

 
## Краткий вывод:
тот код создает CSV-файл с названием "rows_300.csv" и записывает в него данные, представляющие из себя строки с номером, текущей секундой и текущим микросекундным временем. Для этого используется модуль csv для записи в файл в формате CSV, модуль datetime для получения текущей секунды и микросекунды, а также time.sleep(0.01) для приостановки выполнения программы на 0.01 секунды между записями.

# Самостоятельные работы
   ## Самотоятельная работа 1


  ```python
from collections import Counter
import re

def count_words(filename):
    with open(filename, 'r', encoding='utf-8') as file:
        content = file.read()
        words = re.findall(r'\b\w+\b', content.lower())  
        word_count = len(words)
        most_common_word, count = Counter(words).most_common(1)[0]

        print(f"Количество слов в тексте: {word_count}")
        print(f"Самое часто встречающееся слово: '{most_common_word}' (встречается {count} раз)")

if __name__ == "__main__":
    filename = "input.txt"
    count_words(filename)
```
  ### Результат
  ![11](https://github.com/armuane/laba7/blob/main/11.png?raw=true)
![111](https://github.com/armuane/laba7/blob/main/11_1.png?raw=true)

 
## Краткий вывод:
from collections import Counter: Импорт класса Counter из модуля collections, который используется для подсчета количества вхождений элементов в последовательность.

import re: Импорт модуля re для работы с регулярными выражениями.

def count_words(filename): Определение функции count_words, которая принимает имя файла в качестве аргумента.

with open(filename, 'r', encoding='utf-8') as file:: Открытие файла в режиме чтения с использованием конструкции with, чтобы автоматически закрыть файл после завершения работы с ним.

content = file.read(): Считывание содержимого файла в переменную content.

words = re.findall(r'\b\w+\b', content.lower()): Использование регулярного выражения для извлечения всех слов из текста. Регулярное выражение \b\w+\b ищет все слова в тексте.

word_count = len(words): Подсчет общего количества слов в тексте.

most_common_word, count = Counter(words).most_common(1)[0]: Использование класса Counter для подсчета количества каждого уникального слова и определение самого часто встречающегося слова и его количества.

Вывод результатов анализа: Количество слов в тексте и самое часто встречающееся слово с их количеством выводятся на экран.

if __name__ == "__main__":: Этот блок кода выполняется только в том случае, если скрипт запущен напрямую (а не импортирован как модуль). Здесь устанавливается имя файла (filename), который будет анализироваться функцией count_words, и затем вызывается сама функция.

  ## Самотоятельная работа 2


  ```python
import json
import os
from datetime import datetime

def record_expense(expense, amount, category):
    timestamp = datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    entry = {"timestamp": timestamp, "expense": expense, "amount": amount, "category": category}
    return entry

def save_to_file(entries, filename):
    with open(filename, 'w') as file:
        json.dump(entries, file, indent=2)

def load_from_file(filename):
    if os.path.exists(filename):
        with open(filename, 'r') as file:
            entries = json.load(file)
        return entries
    else:
        return []

def display_entries(entries):
    if entries:
        for entry in entries:
            print(f"{entry['timestamp']} - {entry['expense']} ({entry['category']}): ${entry['amount']}")
    else:
        print("Нет записей о расходах.")

def main():
    filename = "expenses.json"

    while True:
        print("\n1. Добавить расход")
        print("2. Просмотреть все расходы")
        print("3. Выход")

        choice = input("Выберите действие (1/2/3): ")

        if choice == '1':
            expense = input("Введите описание расхода: ")
            amount = float(input("Введите сумму: "))
            category = input("Введите категорию: ")

            entries = load_from_file(filename)
            new_entry = record_expense(expense, amount, category)
            entries.append(new_entry)
            save_to_file(entries, filename)
            print("Расход успешно добавлен!")

        elif choice == '2':
            entries = load_from_file(filename)
            display_entries(entries)

        elif choice == '3':
            print("Программа завершена.")
            break

        else:
            print("Неверный выбор. Пожалуйста, введите 1, 2 или 3.")

if __name__ == "__main__":
    main()
```
  ### Результат
  ![12](https://github.com/armuane/laba7/blob/main/12.png?raw=true)

 
## Краткий вывод:
import json: Импорт модуля для работы с JSON-форматом, который используется для сохранения и загрузки данных.

import os: Импорт модуля для работы с операционной системой, используется для проверки существования файла.

from datetime import datetime: Импорт функции datetime из модуля datetime для работы с датой и временем.

record_expense(expense, amount, category): Функция для записи информации о расходе. Создается словарь entry, содержащий метку времени, описание расхода, сумму и категорию расхода.

save_to_file(entries, filename): Функция для сохранения записей в файл в формате JSON. Используется json.dump() для записи данных в файл.

load_from_file(filename): Функция для загрузки записей из файла JSON. Проверяет существование файла, если файл существует, используется json.load() для загрузки данных из файла.

display_entries(entries): Функция для отображения всех записей о расходах. Выводит информацию о каждом расходе, включая дату, описание, сумму и категорию.

main(): Основная функция программы, содержащая цикл while True, в котором предлагается пользователю выбрать действие: добавить расход, просмотреть все расходы или завершить программу.

Программа использует input() для ввода пользовательских данных и выводит информацию в консоль.

if __name__ == "__main__":: Этот блок кода гарантирует, что код будет выполнен, только если скрипт запущен напрямую (а не импортирован как модуль).
  ## Самотоятельная работа 3


  ```python
def analyze_text(file_path):
    try:
        with open(file_path, 'r', encoding='utf-8') as file:
            content = file.read()


            latin_letters_count = sum(1 for char in content if char.isalpha() and char.isascii())


            words = content.split()
            words_count = len(words)


            lines_count = content.count('\n') + 1


            print(f"Количество букв латинского алфавита: {latin_letters_count}")
            print(f"Количество слов: {words_count}")
            print(f"Количество строк: {lines_count}")

    except FileNotFoundError:
        print(f"Файл '{file_path}' не найден.")
    except Exception as e:
        print(f"Произошла ошибка: {e}")

if __name__ == "__main__":
    file_path = "input.txt"
    analyze_text(file_path)
```
  ### Результат
  ![13](https://github.com/armuane/laba7/blob/main/13.png?raw=true)

 
## Краткий вывод:
def analyze_text(file_path):: Определение функции analyze_text, которая принимает путь к файлу в качестве аргумента.

try:: Начало блока обработки исключений. Код внутри этого блока будет выполняться, и если возникнет ошибка, программа перейдет к обработке исключений.

with open(file_path, 'r', encoding='utf-8') as file:: Открытие файла в режиме чтения с использованием контекстного менеджера with. Файл будет автоматически закрыт после выполнения блока кода внутри with.

content = file.read(): Считывание всего содержимого файла и сохранение его в переменной content.

latin_letters_count = sum(1 for char in content if char.isalpha() and char.isascii()): Подсчет количества букв латинского алфавита в тексте. Используется генератор списка и функция sum().

words = content.split(): Разделение текста на слова.

words_count = len(words): Подсчет количества слов в тексте.

lines_count = content.count('\n') + 1: Подсчет количества строк в тексте. Каждая строка заканчивается символом новой строки ('\n').

print(f"Количество букв латинского алфавита: {latin_letters_count}"): Вывод статистики: количество букв латинского алфавита.

print(f"Количество слов: {words_count}"): Вывод статистики: количество слов.

print(f"Количество строк: {lines_count}"): Вывод статистики: количество строк.

except FileNotFoundError:: Обработка исключения, если файл не найден.

except Exception as e:: Обработка общих исключений. Выводит сообщение об ошибке.

if __name__ == "__main__":: Этот блок кода будет выполнен только при запуске программы напрямую (а не при импорте как модуля).

file_path = "input.txt": Указание пути к файлу. Замените на свой путь к файлу перед запуском программы.

analyze_text(file_path): Вызов функции analyze_text с указанным путем к файлу.
  ## Самотоятельная работа 4


  ```python
def censor_sentence(sentence, forbidden_words):
    for forbidden_word in forbidden_words:
        sentence = sentence.replace(forbidden_word, '*' * len(forbidden_word))
    return sentence

def load_forbidden_words(file_path):
    try:
        with open(file_path, 'r', encoding='utf-8') as file:
            forbidden_words = file.read().split()
        return forbidden_words
    except FileNotFoundError:
        print(f"Файл '{file_path}' не найден.")
        return []
    except Exception as e:
        print(f"Произошла ошибка при чтении файла: {e}")
        return []

if __name__ == "__main__":
    forbidden_words_file = "input.txt"
    sentence = input("Введите предложение: ")

    forbidden_words = load_forbidden_words(forbidden_words_file)

    if forbidden_words:
        censored_sentence = censor_sentence(sentence.lower(), forbidden_words)
        print("Цензурированное предложение:")
        print(censored_sentence)
    else:
        print("Не удалось загрузить запрещенные слова.")
```
  ### Результат
  ![14](https://github.com/armuane/laba7/blob/main/14.png?raw=true)

 
## Краткий вывод:
def censor_sentence(sentence, forbidden_words):: Это определение функции censor_sentence, которая принимает предложение и список запрещенных слов в качестве аргументов.

for forbidden_word in forbidden_words:: Это цикл for, который перебирает каждое запрещенное слово в списке forbidden_words.

sentence = sentence.replace(forbidden_word, '*' * len(forbidden_word)): Для каждого запрещенного слова выполняется замена этого слова в предложении на строку, состоящую из звездочек (*), количество которых равно количеству букв в запрещенном слове.

return sentence: Возвращается цензурированное предложение.

def load_forbidden_words(file_path):: Это определение функции load_forbidden_words, которая принимает путь к файлу с запрещенными словами в качестве аргумента.

with open(file_path, 'r', encoding='utf-8') as file:: Открытие файла в режиме чтения с использованием контекстного менеджера with.

forbidden_words = file.read().split(): Считывание содержимого файла и разделение его на слова. Полученные слова сохраняются в списке forbidden_words.

return forbidden_words: Возвращается список запрещенных слов.

if __name__ == "__main__":: Этот блок кода будет выполнен только при запуске программы напрямую (а не при импорте как модуля).

forbidden_words_file = "input.txt": Указание пути к файлу с запрещенными словами. Замените на свой путь к файлу перед запуском программы.

sentence = input("Введите предложение: "): Получение предложения от пользователя через ввод с клавиатуры.

forbidden_words = load_forbidden_words(forbidden_words_file): Загрузка запрещенных слов из файла.

if forbidden_words:: Проверка, удалось ли загрузить запрещенные слова.

censored_sentence = censor_sentence(sentence.lower(), forbidden_words): Цензурирование предложения с использованием функции censor_sentence. Предложение приводится к нижнему регистру для удобства сравнения.

print("Цензурированное предложение:"): Вывод заголовка.

print(censored_sentence): Вывод цензурированного предложения.

else:: Ветка выполнится, если не удалось загрузить запрещенные слова.

print("Не удалось загрузить запрещенные слова."): Вывод сообщения об ошибке.
  ## Самотоятельная работа 5


  ```python
def calculate_average_score(file_path):
    try:
        with open(file_path, 'r', encoding='utf-8') as file:
            lines = file.readlines()

            total_score = 0
            total_students = 0

            for line in lines:
                parts = line.strip().split()
                if len(parts) >= 3:
                    try:
                        score = int(parts[-1])
                        total_score += score
                        total_students += 1
                    except ValueError:
                        print(f"Ошибка в формате файла: неверный балл для строки '{line}'.")

            if total_students > 0:
                average_score = total_score / total_students
                print(f"Средний балл студентов: {average_score:.2f}")
            else:
                print("Нет данных о студентах в файле.")

    except FileNotFoundError:
        print(f"Файл '{file_path}' не найден.")
    except Exception as e:
        print(f"Произошла ошибка: {e}")

if __name__ == "__main__":
    file_path = "students.txt"  
    calculate_average_score(file_path)
```
  ### Результат
  ![15](https://github.com/armuane/laba7/blob/main/15.png?raw=true)
## Вывод 
Программа считывает файл "students.txt", извлекает баллы студентов и вычисляет их средний балл. В случае ошибок (например, неверный формат файла или неверный балл), программа выводит соответствующие сообщения об ошибке.
# Общий вывод 
Работа с файлами в программировании – важный аспект, так как это позволяет программам взаимодействовать с внешними источниками данных, сохранять результаты работы и обеспечивать постоянство информации. Программы, работающие с файлами, могут выполнять различные задачи, такие как обработка текстов, анализ данных, учет расходов и другие.

В контексте Python, операции ввода и вывода файлов облегчены с использованием конструкции with open(...) as file:, которая автоматически управляет открытием и закрытием файлов, что снижает вероятность ошибок и обеспечивает безопасную работу с ресурсами.

Программы, работающие с файлами, часто включают в себя операции чтения, записи, обработки данных из файлов, а также управление исключениями для обработки возможных ошибок, таких как отсутствие файла или некорректный формат данных.

Важно учитывать, что работа с файлами может быть разнообразной и зависит от конкретной задачи программы. От учета расходов до анализа текста, эти примеры программ демонстрируют различные аспекты работы с файлами в Python.


 
